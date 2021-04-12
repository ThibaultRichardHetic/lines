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
          v-for="artiste in myJson.artiste"
          :key="artiste.name"
          :style="`height:${pourcentage(artiste.mpm,step_max)}%;`"
        >
          <CpText tag="p" type="value">{{ artiste.mpm }}</CpText>
          <ArtisteCircle :image="artiste.image"/>
        </div>
      </div>
    </div>
    <div class="container--buttons">
      <ButtonText @click.native="changeArtiste()" :type="buttonArtiste" content="Artistes"/>
      <ButtonText @click.native="changeTitre()" :type="buttonTitre" content="Titres"/>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ArtisteCircle from "@/components/01_atoms/ArtisteCircle/ArtisteCircle.vue";
import ButtonText from "@/components/02_molecules/ButtonText/ButtonText.vue";

import data_artiste from "@/assets/data/Artistes.json";

export default {
  name: "MotsUniques",
  components: {
    CpText,
    ArtisteCircle,
    ButtonText
  },
  data() {
    return {
      title: "Nombre de mots par minute",
      steps: [0, 10, 20, 30, 40, 50],
      step_max: 60,
      myJson: data_artiste,
      buttonArtiste: "active",
      buttonTitre: "inactive",
      titres: [
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          mpm: 120
        },
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          mpm: 118
        },
        {
          name: "Oxmo Puccino",
          image: "oxmo-puccino.jpeg",
          mpm: 107
        },
        {
          name: "PNL",
          image: "pnl.jpeg",
          mpm: 101
        },
        {
          name: "Booba",
          image: "booba.jpeg",
          mpm: 92
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
    },
    changeTitre: function() {
      let test = {
        artiste: this.titres
      };
      this.buttonArtiste = "inactive";
      this.buttonTitre = "active";
      this.step_max = 120;
      this.myJson = test;
    },
    changeArtiste: function() {
      this.buttonTitre = "inactive";
      this.buttonArtiste = "active";
      this.step_max = 60;
      this.myJson = data_artiste;
    }
  }
};
</script>

<style lang="scss">
@import "./MotsMinute.scss";
</style>
