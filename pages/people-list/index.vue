<template>
  <div>
    <div class="wrapper">
      <header>
        <Logo class="animeLeft" width="12rem" />
      </header>
      <div v-for="(person, i) in people.results" :key="i" class="list">
        {{ person.name }}
      </div>
      <Button class="animeRight" btn-text="voltar para início" @click="() => handleClick()" />
    </div>
  </div>
</template>

<script lang="ts">
import vue from 'vue'
export default vue.extend({
  async asyncData ({ $axios }) {
    try {
      const people = await $axios.$get('people')
      return { people }
    } catch (error) {
      return error
    }
  },
  methods: {
    handleClick () {
      this.$router.push('/')
    }
  }
})
</script>

<style lang="scss">
  header {
    display: flex;
    justify-content: center;
  }
  .list {
    color: #fff;
  }
  button {
    background-color: #fff;
    color: #000;
  }
</style>
