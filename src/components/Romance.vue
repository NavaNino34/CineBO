<script setup>
// Catálogo de películas de romance
</script>

<template>
  <main class="romance-container">
    <header class="header-section">
      <h1>Catálogo de Películas de Romance</h1>
      <p class="subtitle">Explora nuestras historias de amor favoritas</p>
    </header>

    <div class="products-grid">
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1534447677768-be436bb09401?auto=format&fit=crop&w=400&q=60" alt="La La Land" class="product-img" />
        <div class="card-content">
          <h3>La La Land</h3>
          <p class="description">Una historia de amor y sueños.</p>
          <span class="price">$12.99</span>
          <button class="buy-btn">Comprar</button>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.romance-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 40px 20px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #fff;
  text-align: center;
}

.header-section {
  margin-bottom: 40px;
}

.header-section h1 {
  font-size: 2.5rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 10px;
  line-height: 1.2;
}

.subtitle {
  font-size: 1.1rem;
  color: #a0aec0;
}

.products-grid {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
}

.product-card {
  background: #ffffff;
  border-radius: 12px;
  overflow: hidden;
  width: 280px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease;
  color: #333;
  text-align: left;
}

.product-card:hover {
  transform: translateY(-5px);
}

.product-img {
  width: 100%;
  height: 220px;
  object-fit: cover;
}

.card-content {
  padding: 20px;
}

.product-card h3 {
  font-size: 1.3rem;
  margin-bottom: 8px;
  color: #2d3748;
}

.description {
  font-size: 0.95rem;
  color: #718096;
  margin-bottom: 15px;
  min-height: 40px;
}

.price {
  display: block;
  font-size: 1.4rem;
  font-weight: bold;
  color: #e91e63;
  margin-bottom: 15px;
}

.buy-btn {
  width: 100%;
  background-color: #e91e63;
  color: white;
  border: none;
  padding: 12px;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
  font-size: 1rem;
  transition: background-color 0.2s;
}

.buy-btn:hover {
  background-color: #c2185b;
}
</style>