<script setup>
import { ref } from 'vue';
defineProps(['active', 'items']);
const emit = defineEmits(['changed']);


function setActive(i){
    emit('changed', i);
}
</script>
<template>
    <div class="tabs is-centered">
        <ul>
            <li v-for="(item,i) in items" :class="{'is-active': i === active}" @click="setActive(i)">
                <a>{{ item }}</a>
            </li>
        </ul>
    </div>
</template>