<template>
   <div class="container">
    <h1>
          {{show.title}}
    </h1>
    <div>
      {{show.description}}
    </div>
  </div>
</template>

<script >
  import Vue from 'vue'
  import { MdButton, MdContent, MdTabs } from 'vue-material/dist/components'
  import 'vue-material/dist/vue-material.min.css'
import 'vue-material/dist/theme/default.css'
Vue.use(MdButton)
Vue.use(MdContent)
Vue.use(MdTabs)
  export default{
     async asyncData({params, $http}) {
      const show = await $http.$get('http://localhost:5000/rest/shows/'+params.id);
      return {show};
    }
  }
</script>

<style>

.container{
  text-align: center;
}
</style>
