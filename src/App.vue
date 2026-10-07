<script setup>
import { ref } from 'vue'
import Romance from './components/Romance.vue'

// Variable para controlar qué vista se muestra
const mostrarCatalogo = ref(false)
</script>

<template>
  <!-- Vista de Bienvenida -->
  <main v-if="!mostrarCatalogo" class="welcome-container">
    <h1>Bienvenidoss a CineBox</h1>
    <p class="subtitle">Tu plataforma de gestión y catálogo de películas.</p>
    
    <div class="card">
      <p>Próximamente aquí encontrarás los productos y catálogos disponibles.</p>
      <!-- Al hacer clic, cambia la variable a true para mostrar el catálogo -->
      <button class="explore-btn" @click="mostrarCatalogo = true">Explorar</button>
    </div>
  </main>

  <!-- Vista del Catálogo de Romance -->
  <Romance v-else />
</template>

<style scoped>
.welcome-container {
  max-width: 600px;
  margin: 80px auto;
  text-align: center;
  font-family: Arial, sans-serif;
  color: #333;
}
h1 {
  font-size: 2.5rem;
  color: #2c3e50;
  margin-bottom: 10px;
}
.subtitle {
  font-size: 1.2rem;
  color: #7f8c8d;
  margin-bottom: 30px;
}
.card {
  background: #fdfdfd;
  border: 1px solid #eaeaea;
  border-radius: 8px;
  padding: 30px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
}
.explore-btn {
  background-color: #3498db;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  margin-top: 15px;
}
.explore-btn:hover {
  background-color: #2980b9;
}
</style>