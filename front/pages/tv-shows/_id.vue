<template>
  <div class="container">
    <h1 class="title">
      {{ show.title }}
    </h1>
    <div class="content">
      <div>
        <div>
          <img :src="show.images.show" />
        </div>
        <div class="description">
          {{ show.description }}
        </div>
        <h1 class="showInfo">Show informations</h1>
        <div>Number of seasons : {{ show.seasons }}</div>
        <div>Total number of episodes : {{ show.episodes }}</div>
        <div>Note : {{ show.notes.mean }}</div>
        <div class="genre">Genre</div>
        <div v-for="genre in show.genres" :key="genre">
          {{ genre }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
export default {
  async asyncData({ params, $http }) {
    const show = await $http.$get(
      "http://localhost:5000/rest/shows/" + params.id
    );
    return { show };
  }
};
</script>

<style>
.container {
  text-align: center;
}
.title {
  margin-top: 1em;

  margin-bottom: 1em;
}
.content {
  text-align: center;
  max-width: 75%;
  border-style: solid;
  margin: auto;
}
.description {
  margin-top: 1em;
}
.showInfo {
  text-decoration: underline;
  margin-top: 1em;
  margin-bottom: 1em;
}
.genre {
  font-weight: bold;
}
</style>
