<template>
  <div>
    <h2 class="myTitle">TV-SHOWS</h2>
    <TvFilmList :shows="shows"></TvFilmList>
  </div>
</template>

<script>
  import {TvFilmList} from "../components/TvFilmList";
  import {Button} from "../components/Button";

  export default {
    async asyncData({params, $http}) {
      const shows = await $http.$get('http://localhost:5000/rest/shows');
      return {shows};
    },
    components: {
      TvFilmList,
      Button
    }
  }
</script>

<style>
  .myTitle {
    text-align: center;
    margin: 20px;
  }
</style>
