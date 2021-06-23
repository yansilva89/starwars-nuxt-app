<template>
  <div class="wrapper">
    <header>
      <Logo class="animeLeft" width="12rem" />
    </header>
    <div class="cards-content">
      <CardLink
        v-for="(person, i) in people.results"
        :key="i"
        class="animeRight"
        :card-img="require('~/assets/images/avatars/r2d2.svg')"
        :card-text="person.name"
        :endpoint="`/people-list/person/${i + 1}`"
      />
    </div>
    <Button class="animeRight" btn-text="voltar" @click="() => handleClickToBack()" />
  </div>
</template>

<script lang="ts">
import vue from 'vue'
export default vue.extend({
  async asyncData ({ $axios }) {
    try {
      const people = await $axios.$get('people/')
      return { people }
    } catch (error) {
      return error
    }
  },
  methods: {
    handleClickToback () {
      this.$router.push('/list-links')
    }
  }
})
</script>
