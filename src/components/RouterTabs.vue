<script setup>
import { useRoute, useRouter, RouterLink } from 'vue-router';

const router = useRouter();
const route = useRoute();
</script>
<template>
    <div class="tabs is-centered">
        <ul>
            <li v-for="route in $router.getRoutes()" :class="{'is-active': route.path === $route.path}">
                <RouterLink :to="route.path">{{ route.name }}</RouterLink>
            </li>
        </ul>
    </div>
</template>