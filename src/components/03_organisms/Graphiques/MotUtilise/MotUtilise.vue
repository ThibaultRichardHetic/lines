<template>
  <div class="container--mot-utile">
    <CpText tag="h3" type="ext">{{ title }}</CpText>
    <div class="graph">
      <div class="classement">
        <div
          class="winner"
          v-for="artiste in myJson.artiste"
          :key="artiste.name"
          :style="`width:${pourcentage(artiste.twScore,step_max)}%;`"
        >
          <CpText tag="p" type="value">{{ artiste.twScore }}</CpText>
          <ArtisteCircle :image="artiste.image"/>
          <CpText
            tag="p"
            type="value word"
            :style="`left:${pourcentage(artiste.twScore,step_max) + 4}%;`"
          >{{ artiste.top_word }}</CpText>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ArtisteCircle from "@/components/01_atoms/ArtisteCircle/ArtisteCircle.vue";

import data_artiste from "@/assets/data/Artistes.json";

export default {
  name: "MotUtilse",
  components: {
    CpText,
    ArtisteCircle
  },
  data() {
    return {
      title: "Nombre de mots par minute",
      steps: [0, 10, 20, 30, 40, 50],
      step_max: 60,
      myJson: data_artiste,
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
@import "./MotUtilise.scss";
</style>
