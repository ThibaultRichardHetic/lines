<template>
  <div class="container--hero">
    <div class="hero--bg">
      <div class="hero__text">
        <CpText tag="h1" type="title">{{ title }}</CpText>
        <CpText tag="p" type="main">{{ text }}</CpText>
        <CpText tag="p" type="main">{{ text2 }}</CpText>
      </div>
      <div :class="`hero__artiste n${index}`" v-for="(artiste, index) in artistes" :key="artiste.name">
        <ArtisteCircle :image="`${artiste.url}`"/>
        <TripleText :text="`${artiste.score} mots`" />
      </div>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ArtisteCircle from "@/components/01_atoms/ArtisteCircle/ArtisteCircle.vue";
import TripleText from "@/components/02_molecules/TripleText/TripleText.vue";

export default {
  name: "Hero",
  components: {
    CpText,
    ArtisteCircle,
    TripleText
  },
  data() {
    return {
      title: "DÉCOUVREZ LA RICHESSE DE VOS ARTISTES PRÉFÉRÉES",
      text:
        "Lines est un projet permettant d’analyser les textes de vos artistes afin d’en sortir des données.",
      text2:
        "Vous vous êtes déjà demandé quel rappeur avait le vocabulaire le plus riche ? Celui qui avait le meilleur débit en moyenne ? Les mots les plus utilisés par les artistes ? Lines réponds à vos questions et vous permets même d’essayer par vous-mêmes avec vox textes favoris !",
      artistes: [
        {
          name: "PNL",
          url: "pnl.jpeg",
          score: "865"
        },
        {
          name: "Nekfeu",
          url: "nekfeu.png",
          score: "594"
        },
        {
          name: "Oxmo Puccino",
          url: "oxmo-puccino.jpeg",
          score: "656"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
@import "./Hero.scss";
</style>
