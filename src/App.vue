<script setup>
import { ref, computed } from 'vue';
import ItemList from './ItemList.vue';

let newItem = ref ("");
let i = 1;
let items = ref ([
    {id: i++, name: "Piim", isDone: false},
    {id: i++, name: "Leib", isDone: true},
    {id: i++, name: "Munad", isDone: false}
]);

function addItem() {
    if (newItem.value.trim() !== "") {
        items.value.push({id: i++, name: newItem.value.trim(), isDone: false});
        newItem.value = "";
    }
}

let doneItems = computed(() => items.value.filter(item => item.isDone));
let toDoItems = computed(() => items.value.filter(item => !item.isDone));

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

        <ItemList :items="items" title="Poenimekiri:"></ItemList>
        <ItemList :items="doneItems" title="Ostetud:"></ItemList>
        <ItemList :items="toDoItems" title="Ostmata:"></ItemList>
    </div>
</template>
