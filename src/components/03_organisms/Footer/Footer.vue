<template>
  <div class="container--footer">
    <div class="footer__text">
      <a href="https://fr.louisvuitton.com/fra-fr/homepage/" target="_blank">
        <CpText type="small">Site Louis Vuitton</CpText>
      </a>
      <a href=https://www.richard-thibault.com/ target="_blank">
        <CpText type="small">Mentions Légales</CpText>
      </a>
      <a href=https://www.richard-thibault.com/ target="_blank">
        <CpText type="small">Cookies</CpText>
      </a>
    </div>
    <div class="downloads">
      <ButtonStore color="dark" brand="apple"/>
      <ButtonStore color="dark" brand="android"/>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ButtonStore from "@/components/02_molecules/ButtonStore/ButtonStore.vue";

export default {
  name: "Footer",
  components: {
    CpText,
    ButtonStore
  },
  data() {
    return {
      text: "Louis vuitton test"
    };
  }
};
</script>

<style lang="scss">
@import "./Footer.scss";
</style>
