<script setup>
import {ref} from 'vue';

const name = 'Vue Dinamico';

const counter = ref(0);

const increment =() =>  {
counter.value++;
};

const decrement =() => {

counter.value--;
};

const reset =() => {
  counter.value = 0;

};

 const classCounter = () => {
  if(counter.value === 0) {
    return 'zero';
  }
  if(counter.value > 0) {
    return 'Positive';
  }
  if(counter.value < 0) {
    return 'Negative';
  }
};
</script>

<template> 
  <h1>Hola {{ name.toUpperCase() }}</h1>
  <h2 :class="classCounter"> {{ counter }}</h2>
  <button @click="increment">Incremet</button>
 <button @click="decrement">Decrement</button>
  <button @click="reset">Reset</button> 
  
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