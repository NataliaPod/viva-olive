<template>
  <section class="ba-menu-section">
    <div class="ba-container">
      <div class="ba-menu-section__wrap">
        <h2 class="ba-section-title ba-menu-section__title">Меню</h2>
        <div class="ba-menu-section__inner">
          <div class="ba-menu-section__categories ba-categories">
            <ul class="ba-categories__list">
              <li class="ba-categories__item" v-for="category in allCategories" :key="category.id">
                <a
                  href="#"
                  :id="category.id"
                  @click.prevent="getCategory"
                  class="ba-categories__link"
                >{{ category.name }}</a>
              </li>
            </ul>
          </div>
          <div class="ba-menu-section__list">
            <div class="ba-item__header">
              <h4 class="ba-item__name">Назва страви</h4>
              <h4 class="ba-item__weight">Вага</h4>
              <h4 class="ba-item__price">Ціна</h4>
              <h4 class="ba-item__order">Замовити</h4>
            </div>
            <div class="ba-item__product ba-product" v-for="dish in filteredDishes" :key="dish.id">
              <div class="ba-product__info">
                <h5 class="ba-product__name">{{ dish.name }}</h5>
                <span
                  class="ba-product__description"
                  v-if="dish.description != ''"
                >{{ dish.description }}</span>
              </div>
              <p class="ba-product__weight">{{ dish.weight }}</p>
              <p class="ba-product__price">{{ `${dish.price} грн` }}</p>
              <div class="ba-product__order">
                <div class="ba-product__buttons">
                  <button class="ba-quantity"></button>
                  <p class="ba-product__quantity">0</p>
                  <button class="ba-quantity"></button>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="ba-season__inner">
          <a class="ba-season__inner--btn ba-season__inner--btn--large">
            <span class="ba-season__inner--btn-text">Додати до кошика</span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      activeCat: 1,
      categories: {},
      categoryID: {},
      dishes: {},
    };
  },
  methods: {
    getCategory(event) {
      this.activeCat = event.target.id;
    },
    getCategoryIDs() {
      let ids = [];
      for (const property in this.dishes) {
        // dish id in dish object
        let item = this.dishes[property].categoryId;
        if (ids.length > 0) {
          //   check and add new id
          ids.forEach((element) => {
            if (element != item) {
              ids.push(item);
            }
          });
        } else {
          //   push first id
          ids.push(item);
        }
      }
      // remove duplicates
      let result = [...new Set(ids)];
      return result;
    },
  },
  created() {
    fetch("data/menu.json")
      .then((result) => result.json())
      .then((data) => {
        // console.log(data.menu.menu.categories);
        this.categories = data.menu.menu.categories;
        this.dishes = data.menu.menu.dishes;
      });
  },
  computed: {
    filteredDishes() {
      let catygory = this.activeCat;
      return this.dishes.filter(function (dish) {
        return dish.categoryId == catygory;
      });
    },
    allCategories() {
      let currentCategories = this.getCategoryIDs();
      let allCategories = [];
      currentCategories.forEach((categoryId) => {
        allCategories.push(
          this.categories.filter(function (categorie) {
            return categorie.id == categoryId;
          })
        );
      });
      let result = [];
      allCategories.forEach((array) => {
        result = result.concat(array);
      });
      return result;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/_scss_variable.scss";
.ba-menu-section {
  margin-bottom: 117px;
  background-repeat: no-repeat;
  background-position-y: 50%;
  background-size: 29%;
  background: url("../../assets/img/bg_menu.png") left top no-repeat;
  height: 100%;

  &__wrap {
    margin-bottom: 58px;
    @media screen and (min-width: 1024px) {
      width: 70%;
      margin-left: 30%;
      margin-bottom: 98px;
    }
  }
  &__title {
    text-align: center;
    color: $white;
    position: relative;
    margin-bottom: 35px;
    @media screen and (min-width: 1440px) {
      margin-bottom: 92px;
    }
    &:before {
      content: "";
      position: absolute;
      top: -30px;
      left: 0;
      right: 0;
      height: 72px;
      background: url("../../assets/img/section_bg_title_right.png") no-repeat
        center;
      background-color: transparent;
      background-size: contain;
      z-index: -1;
      @media screen and (min-width: 1440px) {
        top: -100%;
        height: 152px;
      }
    }
  }
  &__add-to-cart {
    display: flex;
    align-items: center;
    justify-content: center;
  }
}

.ba-categories {
  overflow-x: scroll;

  &::-webkit-scrollbar-track {
    border: 1px solid $disable;
    border-radius: 15px;
  }
  &::-webkit-scrollbar {
    width: 12px;
  }
  &__list {
    list-style: none;
    padding-left: 0;

    display: flex;
    align-items: center;
  }

  &__item {
    white-space: nowrap;
  }
  &__item + &__item {
    margin-left: 35px;
  }

  &__link {
    text-decoration: none;
    color: $darcker-color;
    @media screen and (min-width: 1440px) {
      font-size: 24px;
    }
    &--active {
      font-weight: 700;
    }
  }
}

.ba-item {
  &__header {
    display: flex;
    align-items: center;
    justify-content: flex-start;
  }
  &__name {
    width: 60%;
  }
  &__weight {
    width: 20%;
  }
  &__price {
    width: 20%;
  }
}
.ba-product {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-wrap: wrap;
  font-size: 14px;
  @media screen and (min-width: 640px) {
    flex-wrap: nowrap;
    font-size: 20px;
    margin-bottom: 52px;
  }
  &__name {
    margin: 0;
    text-transform: uppercase;
  }
  &__info {
    width: 60%;
    padding-right: 20px;
  }
  &__weight {
    width: 20%;
  }
  &__price {
    width: 20%;
  }
  &__order {
    width: 100%;
    text-align: center;
    @media screen and (min-width: 640px) {
      width: initial;
    }
  }
  &__quantity {
    font-size: 22px;
    margin: 0 10px;
  }
  &__description {
    font-size: 14px;
    @media screen and (min-width: 1440px) {
      font-size: 20px;
    }
  }
  &__buttons {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 35px;
    @media screen and (min-width: 640px) {
      margin-bottom: 0;
    }
  }
}
.ba-quantity {
  border: none;
  width: 50px;
  height: 50px;
  outline: none;
  background-size: cover;
  &:hover,
  &:focus {
    opacity: 0.5;
  }
}
</style>
