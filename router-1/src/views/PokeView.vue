
<script setup>
import {useRoute, UseRouter,} from "vue-router";
import { useGetData } from "@/components/composables/getData";

const route = useRoute();
const router = useRouter();

const { getData, data, loading } = useGetData();

const back = () => {
    router.push("/pokemons");
};


getData('https://pokeapi.co/api/v2/pokemon/${route.params.name');
</script>

<template>
    <p v-if="loading">Cargando Informacion..</p>
    <div v-if="poke">
        <img :src="poke.sprites?.front_default" alt="" />
    <h1>Poke Name: {{ $route.params.name}}</h1>
    </div>
    <h1 v-else>No existe el pokemon</h1>
    <button @click="back" class="btn btn-outline-primar">Volver</button>
</template>
