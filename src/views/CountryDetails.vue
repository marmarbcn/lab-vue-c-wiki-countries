<template>
    <!-- <div v-for="country in countries" :key="country.alpha3Code" v-if="country.alpha3Code === countryDetail"> -->
    <ul class="list-group list-group-flush">
        <li class="list-group-item  text-start">BANDERA </li>
        <!-- <img
                :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
                :alt="country.name.official" /></li> -->
        <li class="list-group-item text-start">
            <h1>Pais</h1>
        </li>
        <li class="list-group-item text-start">Capital</li>
        <li class="list-group-item text-start">Area</li>
        <li class="list-group-item text-start">Borders
            <ul>
                <li class="text-end">are unaffected by this style</li>
                <li class="text-end">will still show a bullet</li>
                <li class="text-end">and have appropriate left margin</li>
            </ul>
        </li>
    </ul>
    <!-- </div> -->
</template>
<script setup>
const props = defineProps(['countries'])

// const getDetails = () => {
//     const params = new URLSearchParams(window.location.search);
//     return params.get('alpha3Code')
// }

// const showDetails = (countriesDetails) => {
//     const countryDetail = countriesDetails.find((countryDetail) => country.alpha3Code === getDetails());
// }

</script>