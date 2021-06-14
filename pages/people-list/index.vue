<template>
  <div class="wrapper">
    <div v-for="(person, i) in people.results" :key="i" class="list">
      {{ person.name }}
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
