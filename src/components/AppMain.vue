<script>
import CardComp from './CardComp.vue';
import SelectComp from'./SelectComp.vue';
import { store } from '../store.js';
import axios from 'axios';

export default {
    name: 'AppMain',
    components: {
        CardComp,
        SelectComp
    },
    data() {
        return {
            store,
            url: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0',
        }
    },
    methods: {
        getCard(typeArchetype) {
            axios.get(this.url, {
                params: {
                    archetype: typeArchetype
                }
            })
            .then((response) => {
                console.log(response.data);
                this.store.cardList = response.data.data;
            })
        }
    },
    created() {
        this.getCard();
    }
}
</script>

<template>
    <main>
        <div class="container mt-4">
            <div class="row row-cols-1 row-cols-md-3 row-cols-lg-5 g-4">
                <SelectComp @changeType="getCard"/>
            </div>

            <div class="row row-cols-1 row-cols-md-3 row-cols-lg-5 g-4">
                <CardComp />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/main.scss' as *;
@use '../styles/partials/reset.scss' as *;

main {
    background-color: $main-color;
}
</style>