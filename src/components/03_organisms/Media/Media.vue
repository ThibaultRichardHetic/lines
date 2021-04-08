<template>
  <div id="video" class="container--media">
    <iframe
      class="video"
      src="https://www.youtube.com/embed/E3tlWFyzG5o?autoplay=1&mute=1&controls=0&loop=1&showinfo=0&playlist=E3tlWFyzG5o&modestbranding=1&iv_load_policy=3"
      frameborder="0"
    ></iframe>
    <div class="media__content">
      <CpText type="hero-title">LV Watches</CpText>
      <CpText type="hero">Travel in time</CpText>
      <div class="downloads">
        <ButtonStore brand="apple"/>
        <ButtonStore brand="android"/>
      </div>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ButtonStore from "@/components/02_molecules/ButtonStore/ButtonStore.vue";

export default {
  name: "Media",
  components: {
    CpText,
    ButtonStore
  }
};
</script>

<style lang="scss">
@import "./Media.scss";
</style>
