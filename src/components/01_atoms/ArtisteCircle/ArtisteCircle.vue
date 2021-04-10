<template>
  <div class="artiste-circle">
    <img :src="require(`@/assets/images/artistes/${image}`)" alt>
  </div>
</template>

<script>
// changer le nom de la class
export default {
  name: "ArtisteCircle",
  props: {
    type: {
      type: String,
      default: "text"
    },
    image: {
      type: String,
      default: "nekfeu.png"
    }
  }
};
</script>


<style lang="scss">
@import "./ArtisteCircle.scss";
</style>