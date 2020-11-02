<template>
  <NuxtLink class="button" :to="to">{{title}}</NuxtLink>
</template>

<script>
    export default {
        name: "Button",
        props: {
          title: String,
          to: String,
        }
    }
</script>

<style scoped>
.button {
  background-color: blue;
  color: white;
  text-decoration: none;
  border-radius: 10px;
  padding: 5px 10px;
}
</style>
