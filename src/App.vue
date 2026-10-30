<template>
  <div class="container">
    <h1>Botiga de gadgets</h1>
    <div class="content">
      <CategoryList />
      <Cart />
    </div>
  </div>
</template>

<script setup>
import { reactive ,provide } from 'vue';
import CategoryList from './components/CategoryList.vue';
import Cart from './components/Cart.vue';

const cart = reactive([])
const products = [
  { name: "Auriculars Wireless 🎧", price: 50 },
  { name: "Smartwatch ⌚", price: 120 },
  { name: "Teclat Mecànic ⌨️", price: 80 },
  { name: "Altaveu Bluetooth 🔊", price: 60 }
]

provide('cart', cart)
provide('products', products)

</script>

<style>
body {
  font-family: Arial, sans-serif;
  background: #f5f5f5;
}

.container {
  max-width: 1000px;
  margin: 2rem auto;
  background: white;
  border: 1px solid #ddd;
  border-radius: 12px;
  padding: 2rem;
}

.content {
  display: flex;
  gap: 2rem;
}

.cart {
  width: 300px;
}
</style>