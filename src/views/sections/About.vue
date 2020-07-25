<template>
  <section class="ba-section__about">
    <div class="row">
      <div class="column column large-6 medium-8 small-12">
        <h2
          class="ba-section__about__title ba-section__about__title--about"
        >Ресторан "VIVA OLIVE" запрошує всіх бажаючих на обід!</h2>
        <div class="row">
          <div class="column">
            <div class="ba-section__about--desc">
              <p>
                Наш ресторан може запропонувати Вам послуги найвищого рівня (літня тераса, затишний закритий зал, домашня атмосфера). Наші шеф-кухарі задовольнять самі витончені запити гурманів. Всі наші страви припадуть до смаку як дітям, так і доросл им шанувальникам вишуканої кухні.
                Гурмани зможуть по достоїнству оцінити всі наші страви!
                Наш ресторан може запропонувати Вам домашній затишок в поєднанні з високою якістю обслуговування і величезним асортиментом цікавих страв.
              </p>
            </div>
          </div>
          <!-- /.column -->
        </div>
        <!-- /.row -->
      </div>
      <!-- /.column -->
    </div>
  </section>
  <!-- /.ba-section__about -->
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

.ba-section__about {
  padding: 110px 0 23px;
  background: url("../../assets/img/side-decoration.png") right top no-repeat;
  background-size: contain;
  height: 100%;

  @media (min-width: 1024px) {
    background: url("../../assets/img/side-decoration.png") right top no-repeat;
    background-size: contain;
    height: 100%;
  }
}
</style>