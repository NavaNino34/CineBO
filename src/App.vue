<script setup>
import { ref } from 'vue'
<<<<<<< HEAD
import Terror from './components/Terror.vue'
</script>

<template>
  <Terror />
=======
import Romance from './components/Romance.vue'

// Variable que almacena la categoría activa ('romance', 'terror', 'comedia', o null si estamos en el inicio)
const categoriaActiva = ref(null)
</script>

<template>
  <!-- Vista de Bienvenida con los tres botones -->
  <main v-if="categoriaActiva === null" class="welcome-container">
    <h1>Bienvenidoss a CineBox</h1> <!-- ERROR ENCONTRADO, TITULO MAL ESCRITO, CORREGIDO-->
    <p class="subtitle">Tu plataforma de gestión y catálogo de películas.</p>
    
    <div class="card">
      <p>Selecciona una categoría para comenzar a explorar:</p>
      
      <div class="buttons-group">
        <button class="explore-btn romance-btn" @click="categoriaActiva = 'romance'">Romance</button>
        <button class="explore-btn terror-btn" @click="categoriaActiva = 'terror'">Terror</button>
        <button class="explore-btn comedia-btn" @click="categoriaActiva = 'comedia'">Comedia</button>
      </div>
    </div>
  </main>

  <!-- Vista del Catálogo de Romance -->
  <div v-else-if="categoriaActiva === 'romance'">
    <button class="back-btn" @click="categoriaActiva = null">← Volver al inicio</button>
    <Romance />
  </div>

  <!-- Vista temporal para Terror (puedes crear su componente luego) -->
  <div v-else-if="categoriaActiva === 'terror'" class="fallback-view">
    <button class="back-btn" @click="categoriaActiva = null">← Volver al inicio</button>
    <h2 style="color: white; text-align: center; margin-top: 50px;">Catálogo de Terror (Próximamente)</h2>
  </div>

  <!-- Vista temporal para Comedia (puedes crear su componente luego) -->
  <div v-else-if="categoriaActiva === 'comedia'" class="fallback-view">
    <button class="back-btn" @click="categoriaActiva = null">← Volver al inicio</button>
    <h2 style="color: white; text-align: center; margin-top: 50px;">Catálogo de Comedia (Próximamente)</h2>
  </div>
>>>>>>> origin/feature/ruth-romance
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
.buttons-group {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 20px;
  flex-wrap: wrap;
}
.explore-btn {
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: bold;
  transition: opacity 0.2s;
}
.explore-btn:hover {
  opacity: 0.9;
}
.romance-btn { background-color: #e91e63; }
.terror-btn { background-color: #2d3748; }
.comedia-btn { background-color: #f6ad55; color: #1a202c; }

.back-btn {
  margin: 20px;
  background-color: #4a5568;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
.back-btn:hover {
  background-color: #2d3748;
}
</style>