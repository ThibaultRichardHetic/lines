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
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ArtisteCircle from "@/components/01_atoms/ArtisteCircle/ArtisteCircle.vue";


export default {
  name: "MotUtilse",
  components: {
    CpText,
    ArtisteCircle
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
      words: this.data
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
