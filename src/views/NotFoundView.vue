<script setup>
import { useRoute, useRouter } from "vue-router";

const router = useRouter();

const back = () => {
    router.push('/pokemons')
}
</script>

<template>
    <h1>404</h1>
    <button @click="back" class="btn btn-outline-primary">Regresar</button>
</template>