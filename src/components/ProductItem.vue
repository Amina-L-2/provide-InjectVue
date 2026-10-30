<template>
    <div class="product-item">
        <div class="product-info">
            <span class="name">{{ product.name }}</span>
            <span class="price">{{ product.price }}€</span>     
        </div>
        <button @click="addToCart">Add to cart</button>
    </div>
</template>

<script setup>
import { inject } from 'vue';

const props = defineProps(['product']);
const cart = inject('cart');

const addToCart = () => {
    cart.push(props.product);
    alert(`${props.product.name} added to the cart!`);
}

</script>

<style scoped>
.product-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 0.8rem;
  margin-bottom: 0.8rem;
  background: white;
}

.product-info {
  display: flex;
  gap: 1rem;
}

button {
  background-color: #f9c5d5;
  border: none;
  border-radius: 6px;
  padding: 0.5rem 1rem;
  cursor: pointer;
}

button:hover {
  background-color: #f7aec4;
}
</style>