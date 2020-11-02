<template>
  <div class="container">
    <div v-for="show in shows" :key="show.id">
      {{show.title}}
    </div>
  </div>
</template>

<script>
  // import Vue from 'vue'

  export default {
    async asyncData({params, $http}) {
      const shows = await $http.$get('http://localhost:5000/rest/shows');
      return {shows};
    }
  }
</script>

<style>
</style>
