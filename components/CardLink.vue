<template>
  <div class="card-link" @click="() => $emit('click')">
    <h3>{{ cardText }}</h3>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    cardText: {
      type: String,
      default: null
    }
  }
})
</script>

<style lang="scss">
  .card-link {
    display: flex;
    justify-content: center;
    align-items: center;
    transition: background-color 0.5s ease;
    background-color: #f1e63a;
    width: calc(100% / 5 - 1rem);
    margin-right: 1rem;
    min-height: 5rem;
    border-radius: 5px;
    padding: 1rem;
    margin-bottom: 1rem;
    cursor: pointer;
    &:hover {
      background-color: #dca918;
    }
    &:last-child {
      margin-right: 0;
    }
    h3 {
      color: #000;
    }
  }
</style>
