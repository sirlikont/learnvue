<script setup>
import { ref } from 'vue';

let message = ref ("Hello Vue 3 with Vite and Bun!");

function model(event) {
   console.log(event);
   message.value = event.target.value;
}
</script>

<template>  
    <div class="container content mt-5">
        <button class="button is-primary is-light mt-5" @click="message = 'Hello KTA24!'">A Bulma Button</button>
         <input class="input" :value="message" @input="model"/>
        <h1>{{ message }}</h1>
    </div>
</template>
