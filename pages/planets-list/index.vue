<template>
  <div class="wrapper">
    <header>
      <Logo class="animeLeft" width="12rem" />
    </header>
    <div class="cards-content">
      <CardLink
        v-for="(planet, i) in planets.results"
        :key="i"
        class="animeRight"
        :card-img="require('~/assets/images/avatars/r2d2.svg')"
        :card-text="planet.name"
        endpoint="/planets-list"
      />
    </div>
  </div>
</template>

<script lang="ts">
import vue from 'vue'
export default vue.extend({
  async asyncData ({ $axios }) {
    try {
      const planets = await $axios.$get('planets/')
      return { planets }
    } catch (error) {
      return error
    }
  },
  methods: {
    handleClick () {
      this.$router.push('/list-links')
    }
  }
})
</script>
