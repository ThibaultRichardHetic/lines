<template>
  <div class="container--header">
    <a class="header__link" href="#articles">
      <CpText>LV Watches</CpText>
    </a>
    <a class="header__link" href="#collection">
      <CpText>Collection</CpText>
    </a>
    <a class="header__link" href="#video">
      <CpText>Vidéo</CpText>
    </a>
    <ButtonStore brand="apple"/>
    <ButtonStore brand="android"/>
  </div>
</template>

<script>

import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ButtonStore from "@/components/02_molecules/ButtonStore/ButtonStore.vue";

export default {
  name: "Header",
  components: {
    CpText,
    ButtonStore
  }
};
</script>

<style lang="scss">
@import "./Header.scss";
</style>
