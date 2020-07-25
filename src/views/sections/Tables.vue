<template>
  <section class="ba-tables">
    <div class="row column ba-container">
      <div class="ba-tables__inner">
        <h2 class="ba-tables__inner--title">{{ section.title }}</h2>
        <img class="ba-tables__inner--img" src="../../assets/img/tables_scheme_img.png" alt />
      </div>
      <!-- /.ba-tables-title__inner -->
    </div>
  </section>
</template>

<script>
export default {
  props: ["section"]
};
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

.ba-tables__inner {
  display: none;
  padding-top: 50px;
  font-size: 25px;

  &--title {
    text-align: center;
    position: relative;
    margin-bottom: 135px;
    font-size: 30px;
    color: $white;

    &:after {
      content: "";
      background-image: url(../../assets/img/bg_shape.png);
      background-size: cover;
      z-index: -1;
      width: 520px;
      height: 157px;
      position: absolute;
      left: -34%;
      top: -154%;

      @include breakpoint(medium) {
        left: -25%;
      }
    }
  }

  @include breakpoint(medium) {
    padding-top: 150px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}
</style>