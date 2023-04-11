<template>
    <div class="card" style="width: 18rem;" v-for="country in countries" :key="country.alpha3Code">
        <div class="card-body">

            <img :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
                :alt="country.name.official" />
            <h6 class="card-subtitle">{{ country.name.official }} </h6>

        </div>
    </div>
</template>

<script setup>
import { RouterLink } from 'vue-router';


const props = defineProps(['countries'])

</script>