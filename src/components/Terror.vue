<template>
  <div class="contenedor">

    <h1>🎃 Biblioteca de Películas de Terror</h1>

    <div class="card">

      <img
        :src="peliculas[indice].imagen"
        :alt="peliculas[indice].titulo"
        class="portada"
      />

      <h2>{{ peliculas[indice].titulo }}</h2>

      <button @click="mostrarSinopsis = !mostrarSinopsis">
        {{ mostrarSinopsis ? 'Ocultar Sinopsis' : 'Ver Sinopsis' }}
      </button>

      <button @click="siguientePelicula">
        Siguiente Película
      </button>

      <p v-if="mostrarSinopsis">
        {{ peliculas[indice].sinopsis }}
      </p>

      <h3>Disponible en:</h3>

      <div class="plataformas">

        <a href="https://www.netflix.com" target="_blank">
          <img
            src="https://cdn-icons-png.flaticon.com/512/5977/5977590.png"
            alt="Netflix"
            class="icono"
          />
        </a>

        <a href="https://www.max.com" target="_blank">
          <img
            src="https://cdn-icons-png.flaticon.com/512/5968/5968890.png"
            alt="Max"
            class="icono"
          />
        </a>

        <a href="https://www.primevideo.com" target="_blank">
          <img
            src="https://cdn-icons-png.flaticon.com/512/5968/5968885.png"
            alt="Prime Video"
            class="icono"
          />
        </a>

      </div>

    </div>

  </div>
</template>

<script setup>
import { ref } from 'vue'

import conjuro from '../assets/conjuro.webp'
import it from '../assets/it.webp'
import monja from '../assets/monja.webp'

const peliculas = [
  {
    titulo: 'El Conjuro',
    imagen: conjuro,
    sinopsis:
      'Los investigadores paranormales Ed y Lorraine Warren ayudan a una familia aterrorizada por una presencia maligna.'
  },
  {
    titulo: 'IT',
    imagen: it,
    sinopsis:
      'Un grupo de niños enfrenta a Pennywise, un ente maligno que adopta la forma de un aterrador payaso.'
  },
  {
    titulo: 'La Monja',
    imagen: monja,
    sinopsis:
      'Una novicia y un sacerdote investigan una misteriosa muerte en un convento de Rumania.'
  }
]

const indice = ref(0)
const mostrarSinopsis = ref(false)

function siguientePelicula() {
  mostrarSinopsis.value = false
  indice.value = (indice.value + 1) % peliculas.length
}
</script>
<!-- Cambio local de Cristopher para la practica de force push -->
<style scoped>
.contenedor {
  background-color: #111;
  color: white;
  min-height: 100vh;
  text-align: center;
  padding: 30px;
}

h1 {
  color: #d32f2f;
  margin-bottom: 30px;
}

.card {
  width: 350px;
  margin: auto;
  background: #222;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 0 15px rgba(255, 255, 255, 0.2);
}

.portada {
  width: 100%;
  height: 450px;
  object-fit: cover;
  border-radius: 10px;
}

button {
  margin: 5px;
  padding: 10px 15px;
  border: none;
  border-radius: 5px;
  background: #c62828;
  color: white;
  cursor: pointer;
}

button:hover {
  background: #e53935;
}

p {
  margin-top: 15px;
  line-height: 1.5;
}

.plataformas {
  margin-top: 15px;
}

.icono {
  width: 50px;
  height: 50px;
  margin: 10px;
  transition: 0.3s;
}

.icono:hover {
  transform: scale(1.15);
}
</style>