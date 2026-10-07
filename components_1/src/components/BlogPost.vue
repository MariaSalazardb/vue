<script setup>
//const props = defineProps(["title", "id", "body", "colorText"]);
 defineProps({
    title: String,
    id: Number,
    body: {
        type: String,
        default: "Sin Descripcion"
    },

 });

</script>

<template>
    <div class="card"> 
        <div class="card-body">
            <h5 class="card-title" > {{ id }} - {{ title }} </h5>
            <p> {{ body }} </p>
            <button @click="$emit('cambiarFavoritos', title)" 
            class="btn btn-outline-primary">
            Favoritos</button>
        </div>
    </div>
</template>