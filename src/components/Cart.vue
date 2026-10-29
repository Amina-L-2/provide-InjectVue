<template>
    <div class="cart">
        <h2>Cart</h2>
        <ul>
            <li v-for="item in cart" :key="item.name">
                {{ item.name }} - {{ item.price }}€
            </li>
        </ul>
        <p class="total">Total: {{ total }}€</p>
        <button @click="deleteCart">Delete cart</button>
    </div>
</template>


<script setup>
import { inject, computed } from 'vue';

const cart = inject('cart');
const total = computed(() =>
    cart.reduce((sum,p) => sum + p.price, 0)
)
const deleteCart = () => {
    cart.splice(0, cart.length);
}
</script>

