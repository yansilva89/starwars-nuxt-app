<template>
  <div class="wrapper">
    <header>
      <Logo class="animeLeft" width="12rem" />
    </header>
    <div class="cards-content">
      <CardLink
        v-for="(starship, i) in starships.results"
        :key="i"
        class="animeRight"
        :card-img="require('~/assets/images/avatars/r2d2.svg')"
        :card-text="starship.name"
        endpoint="/aircrafts-list"
      />
    </div>
  </div>
</template>

<script lang="ts">
import vue from 'vue'
export default vue.extend({
  async asyncData ({ $axios }) {
    try {
      const starships = await $axios.$get('starships/')
      return { starships }
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
