
<script setup>
import {useRoute, UseRouter} from "vue-router";
import { useGetData } from "@/components/composables/getData";

const route = useRoute();
const router = useRouter();

const {get}

const back = () => {
    router.push("/pokemons");
};

const getData = async () => {
    try {
        const { data } = await axios.get(
            `https://pokeapi.co/api/v2/pokemon/${route.params.name}`
        );
        console.log(data);
        poke.value = data;
    } catch (error) {
        console.log(error);
        poke.value= null;
    }
};

getData();
</script>

<template>
    <div v-if="poke">
        <img
            :src="poke.sprites?.front_default" alt=""/>
    <h1>Poke Name: {{ $route.params.name}}</h1>
    </div>
    <h1 v-else>No existe el pokemon</h1>
    <button @click="back" class="btn btn-outline-primar">Volver</button>
</template>
