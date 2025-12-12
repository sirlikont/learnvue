<script setup>
import axios from 'axios';
import { ref } from 'vue';
import CharacterCard from '../components/CharacterCard.vue';

let characters = ref([]);
let info = ref({});

let res = await axios.get('https://rickandmortyapi.com/api/character');
console.log(res);
characters.value = res.data.results;
info.value = res.data.info;

async function next() {
    let res = await axios.get(info.value.next);
    console.log(res);

    characters.value = res.data.results;
    info.value = res.data.info;
}

async function prev() {
    let res = await axios.get(info.value.prev);
    console.log(res);

    characters.value = res.data.results;
    info.value = res.data.info;
}

</script>
<template>
    <div class="container">
         <nav class="is-flex is-justify-content-space-between my-2">
            <button class="button is-primary" @click="prev" :disabled="!info.prev">Previous</button>
            <button class="button is-primary" @click="next" :disabled="!info.next">Next</button>
        </nav>
        <div class="columns is-multiline">
            <div class="column is-one-quarter" v-for="character in characters">
                <CharacterCard :character="character"></CharacterCard>
            </div>
        </div>
    </div>
</template>