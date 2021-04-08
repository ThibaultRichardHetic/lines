<template>
  <router-link to="/" class="tempostyle" :class="`text__${type}`">
    <slot />
  </router-link>
</template>

<script>
export default {
  name: 'CpLink',
  props: {
    type: {
      type: String,
      default:'a',
    }
  },
}
</script>


<style lang="scss">
@import "./CpLink.scss";
</style>