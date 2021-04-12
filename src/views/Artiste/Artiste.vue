<template>
  <div class="page--artiste">
    <Header/>
    <Hero home="1" />
    <Carousel/>
    <Footer/>
  </div>
</template>

<script>

import Header from "@/components/03_organisms/Header/Header.vue";
import Hero from "@/components/03_organisms/Hero/Hero.vue";
import Carousel from "@/components/03_organisms/Carousel/Carousel.vue";
import Footer from "@/components/03_organisms/Footer/Footer.vue";

export default {
  name: "Artiste",
  components: {
    Header,
    Hero,
    Carousel,
    Footer
  },
  data() {
    return {
      text: "Louis vuitton test",
    };
  }
};
</script>

<style lang="scss">
@import "./Artiste.scss"
</style>
