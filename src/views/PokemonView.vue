<script setup>
import { useRoute, useRouter } from "vue-router";
import { useGetData } from '@/composables/getData';
import { useFavoritosStore } from '@/store/favoritos';

const route = useRoute();
const router = useRouter();
const useFavoritos = useFavoritosStore()

const { add,findPoke } = useFavoritos;

const { data, getData, loading, error } = useGetData()
getData(`https://pokeapi.co/api/v2/pokemon/${route.params.name}` )


const back = () => {
    router.push('/pokemons')
}

</script>

<template>
    <p v-if="loading">Cargando información ...</p>
    <div class="alert alert-danger mt-2" v-if="error"> {{ error }}</div>
    <div v-if="data">
        <img :src="data.sprites?.front_default" alt="">
        <h1>Pokeemon {{ data.name }}</h1>
        <h2>Experience  {{ data.base_experience }} </h2>
        <button :disabled="findPoke(data.name)" class="btn btn-primary mb-2" @click="add(data)">Agregar Favoritos</button>
    </div>
    <button @click="back" class="btn btn-outline-primary">Regresar</button>
  
</template>find