<script setup>
const { inicio, fin, maxLength } = defineProps({
  inicio: Number,
  fin: Number,
  maxLength: Number
});

const emit = defineEmits(['next', 'prev']);

const activarSiguiente = () => {
    console.log("mediste al siguiente");
    emit("next");
};
</script>

<template>
   <div class="btn-group" role="group" aria-label="Basic example">

     <button
      @click="emit('prev')"
      type="button"
      class="btn btn-outline-primary"
      :disabled="inicio === 0"
      >
      Previus {{ inicio }}
     </button>

     <button
      @click="activarSiguiente"
      type="button"
      class="btn btn-outline-primary"
      :disabled="fin >= maxLength"
      >
      Next {{ fin }}
     </button>

   </div>
</template>