<script setup>
  import {RouterView} from "vue-router";
  import QuizzesView from "./views/QuizzesView.vue"
</script>

<template>
  <div class="container">
    <RouterView/>
  </div>
</template>

<style scoped>
  .container {
    max-width: 1000px;
    margin: 0 auto
  }
</style>