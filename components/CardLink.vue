<template>
  <div class="card-link" @click="() => handleClick()">
    <img :src="cardImg" alt="">
    <h3>{{ cardText }}</h3>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    cardImg: {
      type: String,
      default: null
    },
    cardText: {
      type: String,
      default: null
    },
    endpoint: {
      type: String,
      default: null
    }
  },
  methods: {
    handleClick () {
      if (this.endpoint) {
        this.$router.push(this.endpoint)
      }
      this.$emit('click')
    }
  }
})
</script>

<style lang="scss">
  .card-link {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    transition: background-color 0.5s ease;
    background-color: #f1e63a;
    min-height: 5rem;
    border-radius: 5px;
    padding: 1rem;
    cursor: pointer;
    &:hover {
      background-color: #dca918;
    }
    img {
      width: 5rem;
    }
    h3 {
      margin-top: 1rem;
      color: #000;
    }
  }
</style>
