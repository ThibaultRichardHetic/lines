<template>
  <div class="home">
    <Header/>
    <Footer/>
  </div>
</template>

<script>

import Header from "@/components/03_organisms/Header/Header.vue";
import Footer from "@/components/03_organisms/Footer/Footer.vue";

export default {
  name: "Home",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      text: "Louis vuitton test"
    };
  }
};
</script>

<style lang="scss">
@import "./Home.scss"
</style>
