<template>
  <div class="app">
    <Navbar />
    <RouterView :countries="data"></RouterView>
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'

import { ref, onMounted } from 'vue';
const url = 'https://ih-countries-api.herokuapp.com/countries';

let data = ref([]);

onMounted(() => {
  fetch(url)
    .then(response => response.json())
    .then(json => {
      data.value = json;
    })
    .catch(error => {
      console.error(error);
    });
});


</script>

<style scoped></style>