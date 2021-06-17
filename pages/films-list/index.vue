<template>
  <div class="wrapper">
    <header>
      <Logo class="animeLeft" width="12rem" />
    </header>
    <div class="cards-content">
      <CardLink
        v-for="(film, i) in films.results"
        :key="i"
        class="animeRight"
        :card-img="require('~/assets/images/avatars/r2d2.svg')"
        :card-text="film.name"
        endpoint="/films-list"
      />
    </div>
  </div>
</template>

<script lang="ts">
import vue from 'vue'
export default vue.extend({
  async asyncData ({ $axios }) {
    try {
      const films = await $axios.$get('films/')
      return { films }
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
