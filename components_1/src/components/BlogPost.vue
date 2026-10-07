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
        </div>
    </div>
</template>