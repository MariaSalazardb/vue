<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <nav class="navbar bg-light">
    <div class="container-sluid">
      <router-link class="navbar-brand" to="/">
      <img
      src="@/assets/logo.svg"
      alt=""
      width="30"
      height="24"
      class="d-line-block align-text-top"  
     />
     PokeApi
      </router-link>
    </div>
      <router-link 
      active-class="active"
      class="btn btn-outline-primary" mr-2
      to="/">
      Home</router-link> 
      <router-link 
      active-class="active"
      class="btn btn-outline-primary" 
      to="/pokemons">
      Pokemons</router-link> 
     
  </nav>
 <div class="container"> </div>
  <RouterView />

</template>