<template>
  <div class="container--carousel">
    <CpText tag="h2" type="title">{{ title }}</CpText>
    <VueSlickCarousel v-bind="settings">
      <div class="container--slide" v-for="artiste in artistes" :key="artiste.name">
        <div class="slide--bg">
          <div class="container--image">
            <img :src="require(`@/assets/images/artistes/${artiste.image}`)" alt>
          </div>
          <div class="content">
            <CpText tag="h4" type="card-title">{{ artiste.name }}</CpText>
            <CpText tag="p" type="card">Titres : {{ artiste.titres }}</CpText>
            <CpText tag="p" type="card">Albums : {{ artiste.albums }}</CpText>
            <CpLink :page="`artiste/${artiste.to}`" type="button-card">Voir +</CpLink>
          </div>
        </div>
      </div>
    </VueSlickCarousel>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import CpLink from "@/components/01_atoms/CpLink/CpLink.vue";

import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";

export default {
  name: "Carousel",
  components: {
    CpText,
    CpLink,
    VueSlickCarousel
  },
  data() {
    return {
      title: "Voir un artiste",
      settings: {
        arrows: false,
        dots: false,
        slidesToShow: 4,
        slidesToScroll: 1,
        infinite: true
      },
      artistes: [
        {
          name: "Oxmo Puccino",
          titres: 37,
          albums: 3,
          image: "oxmo-puccino.jpeg",
          to: "oxmo-puccino"
        },
        {
          name: "PNL",
          titres: 137,
          albums: 3,
          image: "pnl.jpeg",
          to: "pnl"
        },
        {
          name: "JUL",
          titres: 327,
          albums: 7,
          image: "jul.jpeg",
          to: "jul"
        },
        {
          name: "Nekfeu",
          titres: 82,
          albums: 3,
          image: "nekfeu.png",
          to: "nekfeu"
        },
        {
          name: "Oxmo Puccino",
          titres: 37,
          albums: 3,
          image: "oxmo-puccino.jpeg",
          to: "oxmo-puccino"
        },
        {
          name: "PNL",
          titres: 137,
          albums: 3,
          image: "pnl.jpeg",
          to: "pnl"
        },
        {
          name: "JUL",
          titres: 327,
          albums: 7,
          image: "jul.jpeg",
          to: "jul"
        },
        {
          name: "Nekfeu",
          titres: 82,
          albums: 3,
          image: "nekfeu.png",
          to: "nekfeu"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
@import "./Carousel.scss";
</style>
