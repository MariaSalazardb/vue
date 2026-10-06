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
   <div class="container text-center  mt-3">
     <h1>Hola {{ name.toUpperCase() }}</h1>
     <h2 :class="classCounter"> {{ counter }}</h2>
     <div cclass="btn-group">
       <button @click="increment" class="btn btn-success">Incremet</button>
      <button @click="decrement"class="btn btn-danger">Decrement</button>
      <button @click="reset" class="btm btn-secondary">Reset</button> 
      <button @click="add" :disabled="bloquearBtnadd" class="btn btn-primary">Add </button>
     </div>
    
  <ul class="list-group mt-4">
   <li
       class="list-group-item"
       v-for="(num, index) in arrayFavoritos" 
       :key="index">
       {{ num }}
    </li>
  </ul>
</div>
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