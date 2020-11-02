<template>
  <div>
    <ShowTile class="tv" v-for="show in shows" :show="show" />
  </div>
</template>

<script>
    import {ShowTile} from "../.nuxt/components";

    export default {
        name: "TvFilmList",
        props: {
          shows: Array
        },
      components: {
        ShowTile,
      }
    }
</script>

<style scoped>
.tv {

}
</style>
