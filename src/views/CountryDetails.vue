<template>
    <div class="container">
        <div class="mx-auto"><!-- Flag and country -->
            <img class="rounded mx-auto d-block"
                :src="`https://flagpedia.net/data/flags/w580/${country.alpha2Code.toLowerCase()}.webp`"
                :alt="country.name.official" />
            <h1 class="text-center">{{ country.name.official }}</h1>

        </div>
        <hr>
        <div class="row text-start"> <!-- capital -->
            <p class="col">Capital</p>
            <p class="col">{{ country.capital[0] }}</p>
        </div>
        <hr>
        <div class="row text-start"> <!-- area -->
            <p class="col">Area</p>
            <p class="col">{{ country.area }} km</p>
        </div>
        <hr>
        <div class="row text-start"> <!-- borders -->
            <p class="col">Borders</p>
            <ul class="col">
                <li v-for="border in country.borders" :key="border">{{ border }}
                    <!-- <RouterLink :to="`/list/${country.alpha3Code}`">{{ border }}</RouterLink> -->
                </li>
            </ul>



        </div>

    </div>
</template>

<script setup>
const props = defineProps(['country']);
</script>

<style scoped>
.container {
    margin: 20px;
}

img {
    object-fit: cover;
    height: 200px;
}
</style>