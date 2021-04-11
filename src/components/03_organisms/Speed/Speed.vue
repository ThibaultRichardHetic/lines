<template>
  <div class="container--speed">
    <MotsMinute />
    <div class="container--text">
      <CpText tag="h2" type="title purple">{{ title }}</CpText>
      <CpText tag="p" type="main purple">{{ text }}</CpText>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import MotsMinute from "@/components/03_organisms/Graphiques/MotsMinute/MotsMinute";

export default {
  name: "Speed",
  components: {
    CpText,
    MotsMinute
  },
  data() {
    return {
      title: "Débit de paroles",
      text:
        "Rappé vite ça veut pas dire pas rapper bien ? Absolument, néanmoins il est intéréssant de comprendre quels artistes travaillent le plus leurs flows et leurs débit. Est-ce que ce sont les artites ayant le vocabulaire le plus riche ? On vous laisse comparer les 2 graphiques et vous faire votre propre idée."
    };
  }
};
</script>

<style lang="scss">
@import "./Speed.scss";
</style>
