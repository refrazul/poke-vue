<script setup>
import { useRoute, useRouter } from "vue-router";
import { useGetData } from '@/composables/getData'

const route = useRoute();
const router = useRouter();

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

    Name:  {{ data.name }}
    Experience: {{ data.base_experience }}
    <button @click="back" class="btn btn-outline-primary">Regresar</button>
    </div>
  
</template>