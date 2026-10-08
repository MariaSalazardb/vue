<script setup>
import {ref, computed} from 'vue';

import PaginatePost from './components/PaginatePost.vue';
import BlogPost from "./components/BlogPost.vue";
import LoadingSpinner from './components/LoadingSpinner.vue';

const post = ref([]);
const postXpage = 10;
const inicio = ref(0);
const fin = ref(postXpage)
const loading = ref(true);


const favorito = ref("");

const cambiarFavoritos = (title) => {
 favorito.value = title;
};

const next = () => {
  inicio.value = inicio.value + postXpage;
  fin.value = fin.value + postXpage;
};

const prev = () => {
  inicio.value += -postXpage;
  fin.value += -postXpage;
};

fetch('https://jsonplaceholder.typicode.com/posts')
  .then((res) => res.json())
  .then((data) => {
  post.value = data;
  })
  .catch((e) => colsole.log(e))
  .finally(() => {
    setTimeout(() => {
      loading.value = false;
    }, 2000);
  });
  
  const maxLength = computed(() => post.value.length)
</script>

<template>
     <LoadingSpinner v-if="loading" />
  <div class="container" v-else>
   <h1>App</h1>
   <h2> Mis Post Favoritos: {{ favorito }}
   </h2>

    <PaginatePost 
    @next="next" 
    @prev="prev" 
    :inicio ="inicio" 
    :fin = "fin"
    :maxLength="maxLength"
    class="mb-2" />

   <BlogPost
        v-for="post in post.slice(inicio, fin)" 
        :key="post.id" 
        :title="post.title" 
        :id="post.id" 
        :body="post.body"
        :cambiarFavorito="cambiarFavoritos"
        class="mb-2"
        >
   </BlogPost>
  </div>

</template>
