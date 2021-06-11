<template>
  <div class="logo animeLeft" :style="{width}">
    <img src="~/assets/images/sw.svg">
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    width: {
      type: String,
      default: null
    }
  }
})
</script>

<style lang="scss">
  .logo {
    display: flex;
    img {
      width: 100%;
    }
  }
</style>
