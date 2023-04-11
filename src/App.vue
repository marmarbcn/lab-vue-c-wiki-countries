<template>
  <div class="app">
    <Navbar />
    <div class="container text-center">
      <div class="row">
        <div class="col">
          <CountriesList :countries="data" />
        </div>
        <div class="col-7">
          <CountryDetails />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import CountriesList from './views/CountriesList.vue'
import CountryDetails from "./views/CountryDetails.vue"

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

<style></style>