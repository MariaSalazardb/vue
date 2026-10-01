<script setup>
 const name = 'Vue Dinamico'
 const stylecolor = "color: blue"
 const arrayColors = ['red', 'blue', 'peru']
 const activo = false
</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}</h1>
  <h2> {{ arrayColors}}</h2>
  <h2 :style=" 'color: ${arrayColors[2]}' "> Soy Peru</h2>
  <h2> {{ activo ? 'Activo' : 'Inactivo' }} 

  </h2>
</template>

<style>
h1 {
  color: red;
}
</style>