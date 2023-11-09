<template>
    <div class="product-list">
    <h1>Aquí va el listado de productos</h1>
    <ul>
      <li v-for="producto in productes" :key="producto.id" class="product-item">
        <router-link :to="{ name: 'product', params: { id: producto.id } }" class="product-link">
          Ver detalles del producto {{ producto.name }}
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
    const productes = [
        {
            id: 1,
            name: 'MSI AMD Radeon RX 6650 XT GAMING X',
        },
        {
            id: 2,
            name: 'ASUS Dual GeForce RTX 4060 Ti OC Edition',
        },
        {
            id: 3,
            name: 'MSI GeForce RTX 4070 VENTUS 3X E OC',
        },
        {
            id: 4,
            name: 'Sapphire NITRO+ AMD Radeon RX 7800 XT GAMING',
        },
        {
            id: 5,
            name: 'Gigabyte GeForce RTX 4090 GAMING OC',
        }
    ]
</script>

<style scoped>
.product-list {
  max-width: 600px;
  margin: 0 auto;
}

h1 {
  text-align: center;
  color: #333;
}

ul {
  list-style-type: none;
  padding: 0;
}

.product-item {
  margin: 10px 0;
  padding: 10px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}

.product-link {
  text-decoration: none;
  color: #007BFF;
  font-weight: bold;
  transition: color 0.3s ease;
}

.product-link:hover {
  color: #0056b3;
}
</style>