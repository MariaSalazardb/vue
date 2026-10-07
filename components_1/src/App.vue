<script setup>
import ButtonCounter from "./components/ButtonCounter.vue";
import BlogPost from "./components/BlogPost.vue";
import { ref } from 'vue'
  

const post = ref([
  {title: "Post 01", id: 1, body: "descripcion 01"},
  {title: "Post 02", id: 2, body: "descripcion 02"},
  {title: "Post 03", id: 3, body: "descripcion 03"},
  {title: "Post 04", id: 4} 
])
</script>

<template>
  <div class="container">
   <h1>App</h1>
   <ButtonCounter></ButtonCounter>  
   <ButtonCounter></ButtonCounter> 

   <BlogPost
        v-for="post in post" 
        :key="post.id" 
        :title="post.title" 
        :id="post.id" 
        body="post.body">
   </BlogPost>
  </div>

</template>
