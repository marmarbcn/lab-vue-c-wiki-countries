<template>
    <div class="container text-center">
        <div class="row">
            <div class="col overflow-auto scroll">
                <ul class="list-group" style="width: 18rem;">
                    <li class="list-group-item list-group-item-action" v-for="country in countries"
                        :key="country.alpha3Code">
                        <RouterLink :to="`/list/${country.alpha3Code}`">
                            <img :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
                                :alt="country.name.official" />
                            <br>
                            <h6>{{ country.name.official }} </h6>
                        </RouterLink>
                    </li>
                </ul>
            </div>
            <div class="col-7">
                <RouterView :country="country"></RouterView>
            </div>
        </div>
    </div>
</template>

<script setup>
import { watch, ref } from 'vue';
import { useRoute } from 'vue-router';

const props = defineProps(['countries']);
const country = ref({});
const route = useRoute();

watch(
    () => route.params.alpha3Code,
    (newAlpha3Code) => {
        country.value = props.countries.find((country) => country.alpha3Code === newAlpha3Code);
    }
);
</script>
<style scoped>
router-link {
    text-decoration: none;
}

.scroll {
    height: 600px;
}

a {
    text-decoration: none;
    color: black;
}
</style>