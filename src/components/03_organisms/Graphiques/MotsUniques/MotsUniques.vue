<template>
  <div class="container--mots-uniques">
    <CpText tag="h3" type="ext">{{ title }}</CpText>
    <div class="graph">
      <div class="classement">
        <!-- <ArtisteCircle image="oxmo-puccino.jpeg" :style="`left:${pourcentage(7600, step_max)}%`"/> -->
        <ArtisteCircle
          :image="artiste.image"
          hover=true
          :name="artiste.name"
          :score="artiste.mots_uniques"
          v-for="(artiste, index) in artistes"
          :key="index"
          :style="`left:${pourcentage(artiste.mots_uniques, step_max)}%`"
        /> -
      </div>
      <div class="legend">
        <div class="axe"></div>
        <div class="steps">
          <div
            class="step"
            v-for="(step, index) in steps"
            :key="step"
            :style="`left:${index * 19}%;`"
          >
            <CpText tag="span" type="main">{{ step }}</CpText>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ArtisteCircle from "@/components/01_atoms/ArtisteCircle/ArtisteCircle.vue";

export default {
  name: "MotsUniques",
  components: {
    CpText,
    ArtisteCircle
  },
  data() {
    return {
      title: "Nombre de mots unique ",
      steps: [0, 3000, 5000, 7000, 9000, 11000],
      step_max: 12000,
      artistes: [
        {
          name: "Oxmo Puccino",
          image: "oxmo-puccino.jpeg",
          mots_uniques: 7600
        },
        {
          name: "PNL",
          image: "pnl.jpeg",
          mots_uniques: 5431
        },
        {
          name: "JUL",
          image: "jul.jpeg",
          mots_uniques: 3500
        },
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          mots_uniques: 10020
        },
        {
          name: "Booba",
          image: "booba.jpeg",
          mots_uniques: 7200
        }
      ]
    };
  },
  methods: {
    pourcentage: function(a, b) {
      let result = (a * 100) / b;
      result = Math.round(result);
      return result;
    }
  }
};
</script>

<style lang="scss">
@import "./MotsUniques.scss";
</style>
