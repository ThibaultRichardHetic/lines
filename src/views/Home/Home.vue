<template>
  <div class="home">
    <Header/>
    <Hero/>
    <Footer/>
  </div>
</template>

<script>

import Header from "@/components/03_organisms/Header/Header.vue";
import Hero from "@/components/03_organisms/Hero/Hero.vue";
import Footer from "@/components/03_organisms/Footer/Footer.vue";

export default {
  name: "Home",
  components: {
    Header,
    Hero,
    Footer,
  },
  data() {
    return {
      text: "Louis vuitton test"
    };
  }
};
</script>

<style lang="scss">
@import "./Home.scss"
</style>
