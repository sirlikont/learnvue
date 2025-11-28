<script setup>
import { ref } from 'vue';

let newItem = ref ("");
let items = ref (["Piimm", "Leib", "Munad"]);

function addItem() {
    if (newItem.value.trim() !== "") {
        items.value.push(newItem.value.trim());
        newItem.value = "";
    }
}
</script>

<template>  
    <div class="container is-fluid content mt-5">
        <div class="field has-addons">
            <div class="control is-expanded">
                <input @keydown.enter="addItem" v-model="newItem" class="input" type="text" placeholder="Add item">
            </div>
            <div class="control">
                <button class="button is-info" @click="addItem">
                    Add item
                </button>
            </div>
        </div>
        <h2>Poenimekiri:</h2>
        <ul>
            <li v-for="item in items">{{ item }}</li>
        </ul>
    </div>
</template>
