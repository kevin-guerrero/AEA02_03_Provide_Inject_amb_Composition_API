<script setup>
    import { inject, computed } from 'vue';

    const props = defineProps(['product']);
    const cart = inject('cart');

    const total = computed(() => 
        cart.reduce((sum, p)  => sum + p.price, 0)
    );

    const buidaCarret = () => {
        cart.splice(0, cart.length)
    }
    
</script>

<template>
    <div class="cart">
        <h2>Carret</h2>
        <ul>
            <li v-for="item in cart" 
            :key="item.name"> 
            {{ item.name }} - {{ item.price }}
            </li>
        </ul>
        <p class="total"> Total: {{ total }}€ </p>
    </div>
    <button @click="buidaCarret">🗑️ Buida carret</button>
</template>