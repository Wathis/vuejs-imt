<template>
    <div class="tile">
      <div class="container">
        <img :src="show.images.poster " width="40" alt="">
        <div class="titre">
          <h4>{{show.title}}</h4>
          <a class="betaserie" :href="show.resource_url">Lien betaserie</a>
        </div>
        <NuxtLink class="more" :to="'/tv-shows/' + show.id">Détails</NuxtLink>
      </div>
    </div>
</template>

<script>
    export default {
        name: "ShowTile",
        props: {
          show: Object
        }
    }
</script>

<style scoped>
  .tile {
    box-shadow: 1px 6px 24px 4px rgba(0,0,0,0.2);
    border-radius: 10px;
    text-decoration: none;
    color: gray;
    background-color: white;
    padding: 10px;
    margin: 10px;
    display: block;
    position: relative;
  }

  .container {
    display: flex;
  }
  .titre {
    padding-left: 20px;
  }
  .betaserie {
    text-decoration: none;
    color: grey;
  }
  .more {
    text-decoration: none;
    font-size: 10px;
    position: absolute;
    color: white;
    right: 20px;
    border-radius: 10px;
    background-color: grey;
    padding: 5px;
  }
</style>
