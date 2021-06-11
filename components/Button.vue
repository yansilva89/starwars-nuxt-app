<template>
  <button @click="() => $emit('click')">
    {{ btnText }}
  </button>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    btnText: {
      type: String,
      default: null
    }
  }
})
</script>

<style lang="scss">
  button {
    transition: background-color 0.5s ease;
    background-color: #f2e73a;
    color: #000;
    height: 4rem;
    transition: width 0.1s ease;
    width: 15rem;
    border-radius: 5px;
    font-size: 1.3rem;
    letter-spacing: -2px;
    cursor: pointer;
    &:hover, &:active {
      background-color: #dca918;
    }
    &:hover {
      width: 15.5rem;
    }
  }
</style>
