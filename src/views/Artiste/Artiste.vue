<template>
  <div class="page--artiste">
    <Header/>
    <Hero home="1" />
    <div v-for="artiste in myJson.artiste" :key="artiste.name">
      <div v-if="$route.params.id === artiste.to">
        <MedTime :data="artiste"/>
      </div>
    </div>
    <Carousel/>
    <Footer/>
  </div>
</template>

<script>

import Header from "@/components/03_organisms/Header/Header.vue";
import Hero from "@/components/03_organisms/Hero/Hero.vue";
import MedTime from "@/components/03_organisms/Graphiques/MedTime/MedTime.vue";
import Carousel from "@/components/03_organisms/Carousel/Carousel.vue";
import Footer from "@/components/03_organisms/Footer/Footer.vue";

import data_artiste from "@/assets/data/Artistes.json";

export default {
  name: "Artiste",
  components: {
    Header,
    Hero,
    MedTime,
    Carousel,
    Footer
  },
  data() {
    return {
      text: "Louis vuitton test",
      myJson: data_artiste
    };
  },
  methods: {
    print: function(a) {
      console.log(a)
      return a;
    }
  }
};
</script>

<style lang="scss">
@import "./Artiste.scss"
</style>
