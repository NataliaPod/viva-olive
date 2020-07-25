<template>
  <section class="ba-section-intro">
    <div class="ba-section-intro__inner">
      <h5 class="ba-section-intro__inner--title">{{section.title}}</h5>
      <p class="ba-section-intro__inner--text">
        {{section.content.text}}
        <br />
        <strong>{{section.content.workingOurs}}</strong>
      </p>
      <div class="ba-section-intro__inner--btn">
        <a class="ba-section-intro__inner--btn-link" :href="section.cta.link">{{section.cta.title}}</a>
      </div>
    </div>
    <!-- /.ba-section-intro__inner -->
    <div class="ba-section-intro__scroll">
      <a class="ba-section-intro__scroll--text" href="#welcome">Scroll</a>
      <a href="#welcome" class="ba-section-intro__scroll--link">
        <img
          class="ba-section-intro__scroll--link-img"
          src="../../assets/img/scroll.png"
          alt="Scroll"
        />
      </a>
    </div>
    <!-- /.ba-container -->
  </section>

  <!-- /.ba-section-intro -->
</template>

<script>
export default {
  props: ["section"]
};
</script>

<style lang="scss">
.ba-section-intro {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background: url("../../assets/img/bg_intro_mob.jpg") center center no-repeat;
  background-size: cover;
  height: 100vh;
  position: relative;
  
  @media (min-width: 768px) {
    background: url("../../assets/img/bg_intro_img.png") center center no-repeat;
    background-size: cover;
    height: 100vh;
  }
  &__inner {
    @media (min-width: 768px) {
      padding-top: 50px;
    }
    @media (min-width: 1440px) {
      padding-top: 150px;
    }
    &--title {
      font-family: Montserrat;
      font-style: normal;
      font-weight: 600;
      font-size: 24px;
      line-height: 30px;
      text-align: center;
      margin: 0;
      @media (min-width: 768px) {
        font-weight: bold;
        font-size: 27px;
      }
      @media (min-width: 1024px) {
        font-size: 35px;
      }
      @media (min-width: 1440px) {
        font-size: 50px;
        line-height: 50px;
      }
    }
    &--text {
      font-family: Montserrat;
      font-style: normal;
      font-weight: normal;
      font-size: 14px;
      line-height: 17px;
      text-align: center;
      margin: 25px 0;
      @media (min-width: 768px) {
        margin: 30px 0;
        font-size: 17px;
        line-height: 25px;
      }
      @media (min-width: 1024px) {
        margin: 35px 0;
        font-size: 20px;
        line-height: 25px;
      }
      @media (min-width: 1440px) {
        margin: 30px 0;
        font-size: 22px;
        line-height: 30px;
      }
    }
    &--btn {
      display: flex;
      justify-content: center;
      @media (min-width: 1440px) {
        padding: 30px;
      }
      &-link {
        padding: 10px 27px;
        border: 2px solid #f8f8f8;
        border-radius: 5px;
        text-decoration: none;
        color: #fff;
        text-transform: uppercase;
        &:hover {
          background: #fff;
          color: #c4cca8;
          transition: 0.7s;
        }
      }
    }
  }
  &__scroll {
    display: block;
    margin: 0 auto;
    position: absolute;
    bottom: 0;
    &:hover {
      transform: scale(1.1);
    }
    &--text {
      font-family: Montserrat;
      font-style: normal;
      font-weight: normal;
      font-size: 18px;
      line-height: 32px;
      text-decoration: none;
      color: #2c2c11;
      opacity: 0.7;
      @media (min-width: 768px) {
        font-size: 22px;
      }
    }
    &--link {
      &-img {
        display: block;
        margin: 0 auto;
        padding: 20px 0;
        width: 20px;
      }
    }
  }
}
</style>