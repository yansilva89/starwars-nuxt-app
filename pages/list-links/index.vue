<template>
  <div class="wrapper">
    <header>
      <Logo class="animeLeft" width="12rem" />
    </header>
    <div class="cards-content">
      <CardLink class="animeRight" card-text="personagens" />
      <CardLink class="animeRight" card-text="planetas" />
      <CardLink class="animeRight" card-text="aeronaves" />
      <CardLink class="animeRight" card-text="filmes" />
      <CardLink class="animeRight" card-text="veículos" />
    </div>
    <Button class="animeRight" btn-text="voltar para início" @click="() => handleClick()" />
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
    margin-bottom: 2.5rem;
  }
  .list {
    color: #fff;
  }
  .cards-content {
    display: flex;
    width: 100%;
  }
  button {
    background-color: #fff;
    color: #000;
  }
</style>
