<template>
    <div class="category-list">
        <h2>Products</h2>
        <div class="products">
            <ProductItem v-for="p in products" :key="p.name" :product="p" />
        </div>
    </div>
</template>


<script setup>
import ProductItem from './ProductItem.vue';
import { inject } from 'vue';

const products = inject('products');
</script>

<style scoped>
.category-list {
  flex: 1;
}

h2 {
  margin-bottom: 1rem;
}

.products {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
</style>