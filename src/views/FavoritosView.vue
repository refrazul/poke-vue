<script setup>
import { useFavoritosStore } from '@/store/favoritos';
import { storeToRefs } from 'pinia';

const useFavoritos = useFavoritosStore()

const { favoritos } = storeToRefs(useFavoritos);
const { remove } = useFavoritos;

</script>

<template>
    <h1>Favoritos</h1>
    <ul class="list-group">
        <li class="list-group-item" v-for="poke in favoritos" :key="poke.id">
            <div>
                {{ poke.name }}
            </div>
            <div>
                <button class="btn btn-sm btn-danger" @click="remove(poke.id)">Eliminar</button>
            </div>
            <div>
                <router-link :to="`/pokemons/${poke.name}`" class="btn btn-sm btn-primary mt-2">Ver Pokemon</router-link>
            </div>

        </li>
    </ul>
</template>