<script setup>
import { ref } from 'vue';
import Tabs from './components/Tabs.vue';
let titles = ref(['Music', 'Documents']);
let contents = ref([
    'Some Cool music',
    'Some Cool documents',
]);
let activeTab = ref(0);

function setActiveTab(i){
    activeTab.value = i;
}
</script>
<template>
     <Tabs :active="activeTab" :items="titles" @changed="setActiveTab"></Tabs>
   <p>{{ contents[activeTab] }}</p>
</template>