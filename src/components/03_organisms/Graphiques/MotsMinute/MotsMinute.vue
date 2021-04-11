<template>
  <div class="container--mots-minute">
    <CpText tag="h3" type="ext purple">{{ title }}</CpText>
    <div class="graph">
      <div class="legend">
        <div class="steps">
          <div
            class="step"
            v-for="step in steps"
            :key="step"
            :style="`top:${pourcentageRevert(step ,step_max)}%;`"
          >
            <CpText tag="span" type="step">{{ step }}</CpText>
          </div>
        </div>
        <div class="axe"></div>
      </div>
      <div class="classement">
        <div
          class="winner"
          v-for="artiste in artistes"
          :key="artiste.name"
          :style="`height:${pourcentage(artiste.mpm,step_max)}%;`"
        >
          <CpText tag="p" type="value">{{ artiste.mpm }}</CpText>
          <ArtisteCircle :image="artiste.image"/>
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
      title: "Nombre de mots par minute",
      steps: [0, 10, 20, 30, 40, 50],
      step_max: 60,
      artistes: [
        {
          name: "Oxmo Puccino",
          image: "oxmo-puccino.jpeg",
          mpm: 30
        },
        {
          name: "PNL",
          image: "pnl.jpeg",
          mpm: 22
        },
        {
          name: "JUL",
          image: "jul.jpeg",
          mpm: 31
        },
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          mpm: 41
        },
        {
          name: "Booba",
          image: "booba.jpeg",
          mpm: 45
        }
      ]
    };
  },
  methods: {
    pourcentageRevert: function(a, b) {
      let result = (a * 100) / b;
      result = 100 - result;
      result = Math.round(result);
      return result;
    },
    pourcentage: function(a, b) {
      let result = (a * 100) / b;
      result = Math.round(result);
      return result;
    }
  }
};
</script>

<style lang="scss">
@import "./MotsMinute.scss";
</style>
