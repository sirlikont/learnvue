<script setup>
import { ref } from 'vue';

let message = ref ("Hello Vue 3 with Vite and Bun!");


</script>

<template>  
    <div class="container content mt-5">
        <button class="button is-primary is-light mt-5" @click="message = 'Hello KTA24!'">A Bulma Button</button>
         <input class="input" v-model="message"/>
        <h1>{{ message.split('').reverse().join('') }}</h1>
    </div>
</template>
