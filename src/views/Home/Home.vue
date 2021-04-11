<template>
  <div class="home">
    <Header/>
    <Hero/>
    <VbLarge/>
    <Speed/>
    <TopWord/>
    <Carousel/>
    <Footer/>
  </div>
</template>

<script>

import Header from "@/components/03_organisms/Header/Header.vue";
import Hero from "@/components/03_organisms/Hero/Hero.vue";
import VbLarge from "@/components/03_organisms/VbLarge/VbLarge.vue";
import Speed from "@/components/03_organisms/Speed/Speed.vue";
import TopWord from "@/components/03_organisms/TopWord/TopWord.vue";
import Carousel from "@/components/03_organisms/Carousel/Carousel.vue";
import Footer from "@/components/03_organisms/Footer/Footer.vue";

export default {
  name: "Home",
  components: {
    Header,
    Hero,
    VbLarge,
    Speed,
    TopWord,
    Carousel,
    Footer,
  },
  data() {
    return {
      text: "Lines test"
    };
  }
};
</script>

<style lang="scss">
@import "./Home.scss"
</style>
