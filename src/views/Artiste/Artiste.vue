<template>
  <div class="container--artiste">
    artiste {{ $route.params.id }}
  </div>
</template>

<script>


export default {
  name: "Artiste",
  components: {
  },
  data() {
    return {
      text: "Louis vuitton test"
    };
  }
};
</script>

<style lang="scss">
@import "./Artiste.scss"
</style>
