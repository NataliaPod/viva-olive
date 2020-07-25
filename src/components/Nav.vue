<template>
  <nav class="ba-nav vertical-align">
    <ul class="ba-nav__menu show-for-large">
      <li>
        <router-link to="/">Головна</router-link>
      </li>
      <li>
        <router-link to="/menu">Меню</router-link>
      </li>
      <li>
        <router-link to="/gallery">Фотогалерея</router-link>
      </li>
      <li>
        <router-link to="/news">Новини</router-link>
      </li>
    </ul>
    <!-- /.menu -->
    <div class="ba-nav__logo">
      <img src="@/assets/logo.png" alt="Viva-olive" />
    </div>
    <!-- /.ba-nav__logo -->
    <div class="ba-nav__rigth show-for-large">
      <div class="ba-nav__right--contacts">
        <ul class="ba-nav__menu show-for-medium">
          <li>
            <router-link to="/contacts">Контакти</router-link>
          </li>
        </ul>
      </div>
      <!-- /.ba-nav__right--contacts -->
      <div class="ba-nav__cardicon">
        <svg
          width="36"
          height="49"
          viewBox="0 0 36 49"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M33 14.625H3V42.75C3 43.5788 3.26339 44.3737 3.73223 44.9597C4.20107 45.5458 4.83696 45.875 5.5 45.875H30.5C31.163 45.875 31.7989 45.5458 32.2678 44.9597C32.7366 44.3737 33 43.5788 33 42.75V14.625ZM0.5 11.5V42.75C0.5 44.4076 1.02678 45.9973 1.96447 47.1694C2.90215 48.3415 4.17392 49 5.5 49H30.5C31.8261 49 33.0979 48.3415 34.0355 47.1694C34.9732 45.9973 35.5 44.4076 35.5 42.75V11.5H0.5Z"
            fill="#747436"
          />
          <path
            d="M18 3.6875C16.3424 3.6875 14.7527 4.5106 13.5806 5.97573C12.4085 7.44086 11.75 9.428 11.75 11.5H9.25C9.25 8.59919 10.1719 5.8172 11.8128 3.76602C13.4538 1.71484 15.6794 0.5625 18 0.5625C20.3206 0.5625 22.5462 1.71484 24.1872 3.76602C25.8281 5.8172 26.75 8.59919 26.75 11.5H24.25C24.25 9.428 23.5915 7.44086 22.4194 5.97573C21.2473 4.5106 19.6576 3.6875 18 3.6875Z"
            fill="#747436"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M25.1351 22.8937C25.2515 23.0389 25.3439 23.2113 25.4069 23.4011C25.4699 23.591 25.5023 23.7945 25.5023 24C25.5023 24.2055 25.4699 24.409 25.4069 24.5988C25.3439 24.7887 25.2515 24.9611 25.1351 25.1062L17.6351 34.4812C17.519 34.6267 17.3811 34.7422 17.2292 34.821C17.0773 34.8997 16.9145 34.9403 16.7501 34.9403C16.5857 34.9403 16.4229 34.8997 16.271 34.821C16.1192 34.7422 15.9812 34.6267 15.8651 34.4812L12.1151 29.7937C11.8804 29.5003 11.7485 29.1024 11.7485 28.6875C11.7485 28.2726 11.8804 27.8746 12.1151 27.5812C12.3498 27.2878 12.6682 27.123 13.0001 27.123C13.3321 27.123 13.6504 27.2878 13.8851 27.5812L16.7501 31.1656L23.3651 22.8937C23.4812 22.7482 23.6192 22.6328 23.771 22.554C23.9229 22.4752 24.0857 22.4347 24.2501 22.4347C24.4145 22.4347 24.5773 22.4752 24.7292 22.554C24.8811 22.6328 25.019 22.7482 25.1351 22.8937Z"
            fill="#747436"
          />
        </svg>
        <p>(2)</p>
      </div>
      <!-- /.ba-nav__cardicon -->
      <div class="ba-nav__location">
        <svg
          width="30"
          height="30"
          viewBox="0 0 30 30"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M15 2.5C10.1625 2.5 6.25 6.4125 6.25 11.25C6.25 17.8125 15 27.5 15 27.5C15 27.5 23.75 17.8125 23.75 11.25C23.75 6.4125 19.8375 2.5 15 2.5ZM15 14.375C14.1712 14.375 13.3763 14.0458 12.7903 13.4597C12.2042 12.8737 11.875 12.0788 11.875 11.25C11.875 10.4212 12.2042 9.62634 12.7903 9.04029C13.3763 8.45424 14.1712 8.125 15 8.125C15.8288 8.125 16.6237 8.45424 17.2097 9.04029C17.7958 9.62634 18.125 10.4212 18.125 11.25C18.125 12.0788 17.7958 12.8737 17.2097 13.4597C16.6237 14.0458 15.8288 14.375 15 14.375Z"
            fill="#747436"
          />
        </svg>
        <select class="ba-nav__location--select" name="location" id>
          <option value="poltava">Полтава</option>
          <option value="kremenchuk">Кременчуг</option>
          <option value="sumy">Суми</option>
        </select>
      </div>
      <!-- /.ba-nav__location -->
    </div>
    <!-- /.ba-nav__rigth -->
    <button class="menu-icon hide-for-large" @click="toggleMenu"></button>
  </nav>
</template>

<script>
import { eventBus } from "@/main.js";

export default {
  name: "Nav",
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      eventBus.$emit("toggleMenu");
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

.ba-nav {
  display: flex;
  align-items: center;
  justify-content: space-between;

  a {
    text-decoration: none;
    font-size: 20px;
    color: $darcker-color;

    &:hover,
    &:focus {
      font-weight: 700;
    }
  }

  &__menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
    list-style: none;
    padding-left: 0;

    li + li {
      margin-left: 49px;
    }
  }

  &__cardicon {
    display: flex;
    margin-right: 90px;

    svg + p {
      margin-left: 7px;
    }
  }

  &__location {
    display: flex;

    &--select {
      border: none;
      background-color: inherit;
      outline: none;
    }
  }

  &__rigth {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__right--contacts {
    margin-right: 55px;
  }

  &__logo {
    object-fit: contain;
    max-width: 88px;
    position: relative;

    @include breakpoint(medium) {
      max-width: 145px;
    }
  }

  .menu-icon {
    width: 40px;
    height: 22px;

    &:after {
      content: "";
      height: 4px;
      // background: $primary-olive;
    }
  }
}
</style>