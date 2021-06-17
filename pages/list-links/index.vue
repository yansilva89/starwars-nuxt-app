<template>
  <div class="wrapper">
    <header>
      <Logo class="animeLeft" width="12rem" />
    </header>
    <div class="cards-content">
      <CardLink class="animeRight" :card-img="require('~/assets/images/avatars/r2d2.svg')" card-text="personagens" endpoint="/people-list" />
      <CardLink class="animeRight" :card-img="require('~/assets/images/avatars/planet-d.svg')" card-text="planetas" endpoint="/planets-list" />
      <CardLink class="animeRight" :card-img="require('~/assets/images/avatars/aircrafts.svg')" card-text="veículos" endpoint="/vehicles-list" />
      <CardLink class="animeRight" :card-img="require('~/assets/images/avatars/planets.svg')" card-text="aeronaves" endpoint="/aircrafts-list" />
      <CardLink class="animeRight" :card-img="require('~/assets/images/avatars/droid.svg')" card-text="filmes" endpoint="/films-list" />
    </div>
    <Button class="animeRight" btn-text="voltar para início" @click="() => handleClickToBack()" />
  </div>
</template>

<script lang="ts">
import vue from 'vue'
export default vue.extend({
  methods: {
    handleClickToBack () {
      this.$router.push('/')
    }
  }
})
</script>
