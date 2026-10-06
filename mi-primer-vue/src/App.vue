<script setup>
import {ref, computed} from 'vue';

const name = 'Vue Dinamico';

const counter = ref(0);
const arrayFavoritos = ref([]);
const increment =() =>  {
counter.value++;
};

const decrement = () => {

counter.value--;
};

const reset = () => {
  counter.value = 0;

};

const add  = () => {
  arrayFavoritos.value.push(counter.value);
};

const bloquearBtnadd = computed(() => {
  const numSearch = arrayFavoritos.value.find((num) => num === counter.value);
  console.log (numSearch);
  if (numSearch === 0) return true;
  return numSearch ? true : false;
  //return numSearch || numSearch === 0 ? true : false;

});

 const classCounter = computed(() => {
  if(counter.value === 0) {
    return 'zero';
  }
  if(counter.value > 0) {
    return 'Positive';
  }
  if(counter.value < 0) {
    return 'Negative';
  }
 });

</script>

<template> 
  <h1>Hola {{ name.toUpperCase() }}</h1>
  <h2 :class="classCounter"> {{ counter }}</h2>
  <button @click="increment">Incremet</button>
 <button @click="decrement">Decrement</button>
  <button @click="reset">Reset</button> 
  <button @click="add" :disabled="bloquearBtnadd">Add </button>
<br />
{{ araryFavoritos }}

<ul>
  <li v-for="(num, index) in araryFavoritos" :key="index">
    {{ num }}
  </li>
</ul>

</template>

<style>
h1 {
  color: red;
}
.zero {
  color: blue;
}
.positive {
  color: green;
}
.negative {
  color: red;
}

</style>