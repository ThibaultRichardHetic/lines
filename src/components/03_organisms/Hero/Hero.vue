<template>
  <div class="container--hero">
    <div class="hero__banner">
      <div class="banner__video">
        <iframe
          src="https://player.vimeo.com/video/363025350?background=1"
          frameborder="0"
          allow="autoplay; fullscreen; picture-in-picture"
          allowfullscreen="true"
        ></iframe>
      </div>
      <div class="banner__content">
        <img src="@/assets/images/logo-app.png" alt>
        <div class="content">
          <CpText type="hero-title">LV Watches</CpText>
          <CpText type="hero">Travel in time</CpText>
          <div class="downloads">
            <ButtonStore brand="apple"/>
            <ButtonStore brand="android"/>
          </div>
        </div>
      </div>
      <div class="banner__img">
        <img src="@/assets/images/mockup.png" alt>
      </div>
    </div>
    <div class="hero__description">
      <CpText type="description">
        Découvrez la nouvelle application LV Watches.
        <br>Synchronisez votre montre connectée à votre téléphone et explorez toutes les fonctionnalités à portée de main !
      </CpText>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ButtonStore from "@/components/02_molecules/ButtonStore/ButtonStore.vue";

export default {
  name: "Hero",
  components: {
    CpText,
    ButtonStore
  }
};
</script>

<style lang="scss">
@import "./Hero.scss";
</style>
