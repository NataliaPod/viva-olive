<template>
  <header class="ba-header">
    <div class="ba-container">
      <v-nav />
    </div>
  </header>
</template>

<script>
import Nav from "@/components/Nav";

export default {
  name: "Header",
  components: {
    "v-nav": Nav,
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/main";

.ba-header {
  height: 121px;
  background: $olive;
}
</style>