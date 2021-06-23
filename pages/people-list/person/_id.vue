<template>
  <div>
    bla bla bla bla bla
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  async asyncData ({ $axios }) {
    try {
      const people = await $axios.$get('people/')
      return { people }
    } catch (error) {
      return error
    }
  },
  mounted () {
    const idItem: string = this.$route.params.id
  },
  methods: {
    handleClickToback () {
      this.$router.push('/list-links')
    }
  }
})
</script>

<style lang="scss" scoped>
div {
  color: #fff
}
</style>
