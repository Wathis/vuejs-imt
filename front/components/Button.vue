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
  background-color: deepskyblue;
  box-shadow: 1px 6px 24px 4px rgba(0,0,0,0.2);
  text-align: center;
  color: white;
  margin: auto;
  display: block;
  width: 200px;
  text-decoration: none;
  border-radius: 10px;
  padding: 5px 10px;
}
</style>
