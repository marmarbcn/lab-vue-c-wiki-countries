<template>
    <div class="container text-center">
        <div class="row">
            <div class="col overflow-auto scroll">
                <div class="card" style="width: 18rem;" v-for="country in countries" :key="country.alpha3Code">
                    <div class="card-body">
                        <RouterLink :to="`/list/${country.alpha3Code}`">
                            <img :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
                                :alt="country.name.official" />
                            <h6 class="card-subtitle">{{ country.name.official }} </h6>
                        </RouterLink>
                    </div>

                </div>
            </div>
            <div class="col-7">
                <RouterView></RouterView>
            </div>
        </div>
    </div>
</template>

<script setup>

const props = defineProps(['countries'])


</script>
<style scoped>
router-link {
    text-decoration: none;
}

.scroll {
    height: 600px;
}
</style>