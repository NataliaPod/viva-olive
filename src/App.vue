<template>
  <div class="off-canvas-wrapper">
    <div
      v-bind:class="{ 'is-open': isMenuOpen }"
      class="off-canvas position-left"
      id="offCanvas"
      data-off-canvas
    >
      <!-- Your menu or Off-canvas content goes here -->
      <v-mobnav />
    </div>
    <div class="off-canvas-content" data-off-canvas-content>
      <!-- Your page content lives here -->
      <v-header />

      <router-view />

      <v-footer />
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";
import MobNav from "@/components/MobNav";

import { eventBus } from "@/main.js";

export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
  components: {
    "v-header": Header,
    "v-footer": Footer,
    "v-mobnav": MobNav,
  },
  created() {
    eventBus.$on("toggleMenu", () => (this.isMenuOpen = !this.isMenuOpen));
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/main";
</style>
