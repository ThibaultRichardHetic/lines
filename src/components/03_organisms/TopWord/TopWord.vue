<template>
  <div class="container--topword">
    <div class="container--text">
      <CpText tag="h2" type="title">{{ title }}</CpText>
      <CpText tag="p" type="main">{{ text }}</CpText>
    </div>
    <MotUtilise />
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import MotUtilise from "@/components/03_organisms/Graphiques/MotUtilise/MotUtilise";

export default {
  name: "TopWord",
  components: {
    CpText,
    MotUtilise
  },
  data() {
    return {
      title: "Top word",
      text:
        "En tant qu’artiste, il est important de se créer un univers propre, pour se démarquer. Cette création d’univers passe notamment par le choix de mots réccurents. Ce choix ancrera l’auditeur dans l’univers voulu, cru, sombre, digital, lyrique..."
    };
  }
};
</script>

<style lang="scss">
@import "./TopWord.scss";
</style>
