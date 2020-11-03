<template>
    <div class="tile">
      <div class="container">
        <img :src="show.images.poster " width="40" alt="">
        <div class="titre">
          <h4>{{show.title}}</h4>
          <a class="betaserie" :href="show.resource_url">Lien betaserie</a>
        </div>
        <div class="other">
          <div v-if="!show.user.favorited" @click="onClickAddFavourite" class="favourite">
            Ajouter en favoris
          </div>
          <div v-if="show.user.favorited" @click="onClickAddFavourite" class="favourite">
            Enlever des favoris
          </div>
          <NuxtLink class="more" :to="'/tv-shows/' + show.id">Détails</NuxtLink>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
        name: "ShowTile",
        props: {
          show: Object
        },
      data: function(){
        return {
          showData: undefined,
          favorited: false,
        }
      },
      watch: {
        show: function(showNew) {
          this.showData = showNew;
          this.favorited = this.showData.user.favorited;
        }
      },
      methods: {
          async onClickAddFavourite(){
            let res = await this.$http.post('http://localhost:5000/rest/shows/'+ this.showData.id +'/favorites', {isFavorite: !this.favorited});
            if (res.status === 200) {
              this.favorited = !this.favorited;
            }
          }
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
  .other {
    text-decoration: none;
    display: flex;
    position: absolute;
    color: white;
    right: 20px;
  }
  .favourite {
    padding: 5px;
    color: grey;
    cursor: pointer;
  }
  .more {
    text-decoration: none;
    color: white;
    border-radius: 10px;
    background-color: grey;
    padding: 5px;
  }
</style>
