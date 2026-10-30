<template>
    <div class="cart">
        <h2>Cart</h2>

        <p>There are {{ totalItems }} articles in the cart.</p>

        <ul>
            <CartItem
                v-for="item in cart"
                :key="item.name"
                :item="item"
            />
        </ul>
        <p class="total">Total: {{ total }}€</p>
        <button @click="deleteCart">Delete cart</button>
    </div>
</template>


<script setup>
import { inject, computed } from 'vue';
import CartItem from './CartItem.vue';

const cart = inject('cart');

const total = computed(() =>
    cart.reduce((sum,p) => sum + p.price, 0)
)

const totalItems = computed(() => cart.length)

const deleteCart = () => {
    cart.splice(0, cart.length);
}
</script>

<style scoped>
.cart {
  background: white;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 1rem;
}

h2 {
  margin-bottom: 1rem;
}

ul {
  list-style: none;
  padding: 0;
}

.total {
  margin-top: 1rem;
  font-weight: bold;
  text-align: right;
}

button {
  background-color: #f9c5d5;
  border: none;
  border-radius: 6px;
  padding: 0.6rem 1rem;
  cursor: pointer;
  margin-top: 1rem;
}

button:hover {
  background-color: #f7aec4;
}
</style>

