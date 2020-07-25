<template>
  <main>
    <Intro v-bind:section="sections.intro" />
    <About v-bind:section="sections.about" />
    <MenuSection />
    <SeasonMenu />
    <Tables v-bind:section="sections.tables" />
  </main>
</template>

<script>
import Intro from "@/views/sections/Intro";
import About from "@/views/sections/About";
import MenuSection from "@/views/sections/Menu_home";
import SeasonMenu from "@/views/sections/SeasonMenu";
import Tables from "@/views/sections/Tables";

export default {
  name: "Home",
  data() {
    return {
      title: "Home page",
      sections: null
    };
  },
  components: {
    Intro,
    About,
    MenuSection,
    SeasonMenu,
    Tables
  },
  created() {
    fetch("data/page_home.json")
      .then(result => result.json())
      .then(data => {
        console.log(data);

        this.sections = data;
      });
  }
};
</script>

<style>
</style>