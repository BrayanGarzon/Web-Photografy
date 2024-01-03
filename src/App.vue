<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheHome from './views/HomeView.vue'
import TheFooter from './views/footerView.vue'
import TheNav from './views/navView.vue'
import TheScroll from './views/iconScrollView.vue' /*vista del componente scroll */
</script>

<template>
  <div>
    
    <div id="nav">
      <TheNav/> <!-- NAV con posición fija -->
    </div>
    
    
    <div> <!-- Ajusta el margen para evitar que el contenido se solape con el nav -->
      <RouterView /> <!-- Pestañas de la app -->
    </div>
    <TheScroll />
    <TheFooter/> <!-- Footer de la app -->
  </div>
</template>

<style scoped>
  #nav {
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000; /* Ajusta el índice de apilamiento según sea necesario */
  }
  
</style>

