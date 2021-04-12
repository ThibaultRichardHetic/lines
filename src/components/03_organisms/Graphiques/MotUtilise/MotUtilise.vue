<template>
  <div class="container--mot-utile">
    <CpText v-if="type == 'all'" tag="h3" type="ext">{{ title }}</CpText>
    <div class="graph">
      <div class="classement" v-if="type == 'all'">
        <div
          class="winner"
          v-for="artiste in words.artiste"
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

      <div class="classement" v-else-if="type == 'artiste'">
        <CpText tag="h3" type="title">{{ title2 }}</CpText>
        <div
          class="winner"
          v-for="word in artisteWords"
          :key="word.word"
          :style="`width:${pourcentage(word.iteration,350)}%;`"
        >
          <CpText tag="p" type="value">{{ word.iteration }}</CpText>
          <CpText
            tag="p"
            type="value word"
            :style="`left:${pourcentage(word.iteration,350) + 4}%;`"
          >{{ word.word }}</CpText>
        </div>
      </div>
    </div>

    <div v-if="type == 'all'" class="container--buttons">
      <ButtonText @click.native="changeArtiste()" :type="buttonArtiste" content="Artistes"/>
      <ButtonText @click.native="changeTitre()" :type="buttonTitre" content="Titres"/>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ArtisteCircle from "@/components/01_atoms/ArtisteCircle/ArtisteCircle.vue";
import ButtonText from "@/components/02_molecules/ButtonText/ButtonText.vue";

export default {
  name: "MotUtilse",
  components: {
    CpText,
    ArtisteCircle,
    ButtonText
  },
  props: {
    type: {
      type: String,
      default: "all"
    },
    data: {
      type: Object
    }
  },
  data() {
    return {
      title: "Mot le plus utilisé par artiste",
      title2: "Top Word",
      steps: [0, 10, 20, 30, 40, 50],
      step_max: 60,
      artisteWords: this.data.top_words,
      words: this.data,
      buttonArtiste: "active",
      buttonTitre: "inactive",
      titres: [
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          top_word: "Premier",
          twScore: 120
        },
        {
          name: "Nekfeu",
          image: "nekfeu.png",
          top_word: "Menteur",
          twScore: 92
        },
        {
          name: "Oxmo Puccino",
          image: "oxmo-puccino.jpeg",
          top_word: "Temps",
          twScore: 83
        },
        {
          name: "PNL",
          image: "pnl.jpeg",
          top_word: "Abonné",
          twScore: 62
        },
        {
          name: "Booba",
          image: "booba.jpeg",
          top_word: "Argent",
          twScore: 71
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
      this.step_max = 150;
      this.words = test;
    },
    changeArtiste: function() {
      this.buttonTitre = "inactive";
      this.buttonArtiste = "active";
      this.step_max = 60;
      this.words = this.data;
    }
  }
};
</script>

<style lang="scss">
@import "./MotUtilise.scss";
</style>
