<script setup>
import { ref } from 'vue';
import Tabs from './components/Tabs.vue';
import ToDo from './pages/ToDo.vue';
import Modals from './pages/Modals.vue';
import RouterTabs from './components/RouterTabs.vue';

let titles = ref(['ToDo', 'Modals']);
let components = ref([
    ToDo,
    Modals,
]);
let activeTab = ref(0);

function setActiveTab(i){
    activeTab.value = i;
}
</script>
<template>
   <!-- <Tabs :active="activeTab" :items="titles" @changed="setActiveTab"></Tabs> -->
  <!-- <component :is="components[activeTab]"></component> -->
   <RouterTabs></RouterTabs>
   <RouterView></RouterView>
</template>