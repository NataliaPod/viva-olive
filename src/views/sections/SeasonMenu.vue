<template>
  <section class="ba-season">
    <div class="row column ba-container">
      <div class="ba-season__inner">
        <a class="ba-season__inner--btn" @click="onMenu">
          <span class="ba-season__inner--btn-text">Сезонне меню</span>
          <span class="ba-season__inner--btn-icon">
            <img src="../../assets/img/down-arrow.png" alt />
          </span>
        </a>
        <img
          v-show="isVisibleMenu"
          class="ba-season__inner--img"
          src="../../assets/img/season-menu.jpg"
          alt
        />
      </div>
      <!-- /.ba-season__inner -->
    </div>
    <!-- /.ba-container -->
  </section>
  <!-- /.ba-season -->
</template>

<script>
export default {
  data: function () {
    return {
      isVisibleMenu: false,
    };
  },
  methods: {
    onMenu() {
      this.isVisibleMenu = !this.isVisibleMenu;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

.ba-season__inner {
  display: flex;
  flex-direction: column;
  align-items: center;

  &--btn {
    margin: 50px 0;
    padding: 10px;
    border: 2px solid $primary-olive;
    border-radius: 5px;
    text-decoration: none;
    text-transform: uppercase;
    background: $olive;
    color: $primary-olive;
    font-family: Montserrat;
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 27px;
    max-width: 180px;

    &-icon {
      padding-left: 10px;
    }
  }
}
</style>