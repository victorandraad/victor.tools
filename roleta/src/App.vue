<template>
    <nav class="flex gap-10 pl-10 pt-5">
      <a href="#/">
        <img class="size-12" src=".\assets\logo.png" alt="">
      </a>
      <ul class="flex gap-10">
        <li><a href="#/">Início</a></li>
        <li><a href="#/about">Sobre</a></li>
        <li><a href="#/services">Serviços</a></li>
      </ul>
    </nav>
    <br>
    <hr>
    <component :is="currentView"/>
    <rodape/>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue'
  import Home from './Home.vue'
  import About from './About.vue'
  import Services from './Services.vue'
  import rodape from './components/footer.vue'
  import Roleta from './Roleta.vue'

  const routes = {
    '/': Home,
    '/about' : About,
    '/services' : Services,
    '/roleta' : Roleta
  }
  
  const currentPath = ref(window.location.hash)
  
  window.addEventListener('hashchange', () =>{
    currentPath.value = window.location.hash
  })
  
  const currentView = computed(() =>{
    return routes[currentPath.value.slice(1) || '/' || Home]
  })

  </script>
  
  <style scoped>
    ul {
      align-items: center;
      list-style-type: none;
      margin: 0;
      padding: 0;
    }
  
    a {
      color: white;
    }
  </style>