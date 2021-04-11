<template>
  <div class="container--vb-large">
    <div class="container--text">
      <CpText tag="h2" type="title shadow">{{ title }}</CpText>
      <CpText tag="p" type="main">{{ text }}</CpText>
    </div>
    <MotsUniques />
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import MotsUniques from "@/components/03_organisms/Graphiques/MotsUniques/MotsUniques";

export default {
  name: "VbLarge",
  components: {
    CpText,
    MotsUniques
  },
  data() {
    return {
      title: "Vocabulaire le plus large ",
      text: "Il est de notoriété publique que tout les artistes n’utilisent pas le même vocabulaire. Lines vous permets de mettre en lumière cet écart de vocabulaire et de richesses dans le choix des mots. Il est important aussi de rappeler qu’un artiste peut avoir une richesse limitées dans son vocabulaire pour mettre l’emphase sur son univers en reprenant souvent des mots similaires..."
    }
  }
};
</script>

<style lang="scss">
@import "./VbLarge.scss";
</style>
