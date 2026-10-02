<script setup>
 const name = 'Vue Dinamico';
 const objetoFrutas = [
  {
    fruta: 'Manzana',
    price: "$1.00",
    color: 'Rojo',
    descripcion: "La manzana es una fruta deliciosa y saludable que se puede comer cruda o cocida. Es rica en vitaminas y antioxidantes, y viene en una variedad de colores y sabores.",
    stock: 10
  },
  {
    fruta: 'Banana',
    price: "$0.50",
    color: 'Amarillo',
    descripcion: "La banana es una fruta tropical dulce y nutritiva que se puede comer sola o en batidos. Es rica en potasio y fibra.",
    stock: 15
  },
  {
    fruta: 'Naranja',
    price: "$0.75",
    color: 'Naranja',
    descripcion: "La naranja es una fruta cítrica jugosa y refrescante que se puede comer sola o en jugos. Es rica en vitamina C.",
    stock: 20
  }
];
</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}</h1>
  {{ objeto.fruta }}
<ul>

   <template v-for ="item in arraysfrutas" :key="item.name">
    <li v-if="item.stock > 0"{{ item.name }} -{{item.price}}> </li>
    </template>
</ul>
</template>

<style>
h1 {
  color: red;
}
</style>