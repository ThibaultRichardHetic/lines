<template>
  <div class="container--mots-uniques">
    <CpText tag="h3" type="ext">{{ title }}</CpText>
    <div class="graph">
      <div class="classement">
        <ArtisteCircle
          :image="artiste.image"
          hover="true"
          :name="artiste.name"
          :score="artiste.mots_uniques"
          v-for="(artiste, index) in myJson.artiste"
          :key="index"
          :style="`left:${pourcentage(artiste.mots_uniques, step_max)}%`"
        />
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
      title: "Nombre de mots unique",
      steps: [0, 3000, 5000, 7000, 9000, 11000],
      step_max: 12000,
      myJson: data_artiste,
      buttonArtiste: "active",
      buttonTitre: "inactive",
      titres: [
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          mots_uniques: 10020
        },
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          mots_uniques: 9020
        },
        {
          name: "Oxmo Puccino",
          image: "oxmo-puccino.jpeg",
          mots_uniques: 8320
        },
        {
          name: "PNL",
          image: "pnl.jpeg",
          mots_uniques: 6245
        },
        {
          name: "Booba",
          image: "booba.jpeg",
          mots_uniques: 7145
        }
      ]
    };
  },
  methods: {
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
      this.myJson = test;
    },
    changeArtiste: function() {
      this.buttonTitre = "inactive";
      this.buttonArtiste = "active";
      this.myJson = data_artiste;
    }
  }
};
</script>

<style lang="scss">
@import "./MotsUniques.scss";
</style>
