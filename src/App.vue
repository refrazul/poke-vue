<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <nav class="navbar bg-dark navbar-dark">
  <div class="container">
    <RouterLink class="navbar-brand" to="/">
      <img src="@/assets/logo.svg" alt="Logo" width="30" height="24" class="d-inline-block align-text-top">
      PokeAPI
    </RouterLink>
    <div>
      <RouterLink to="/" class="btn btn-outline-primary me-2">Home</RouterLink>
      <RouterLink to="/pokemons" class="btn btn-outline-primary">Pokemons</RouterLink>
    </div>
  </div>
  
</nav>

<div class="container text-center">
  <RouterView />
</div>
  
</template>