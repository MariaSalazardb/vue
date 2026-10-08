<script setup>
import { ref } from 'vue'

import PaginatePost from './components/PaginatePost.vue';
import BlogPost from "./components/BlogPost.vue";

  

const post = ref([]);
const postXpage = 5;
const inicio = ref(0);
const fin = ref(postXpage)


const favorito = ref("");

const cambiarFavoritos = (title) => {
 favorito.value = title;
};

fetch('https://jsonplaceholder.typicode.com/posts')
  .then((res) => res.json())
  .then((data) => {
  post.value = data
  });
</script>

<template>
  <div class="container">
   <h1>App</h1>
   <h2> Mis Post Favoritos: {{ favorito }}
   </h2>
   
      <PaginatePost class="mb-2"/>

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
