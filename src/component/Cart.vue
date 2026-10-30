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

<style scoped>
.cart {
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    background: white;
}

h2 {
    margin: 0 0 16px;
    font-size: 1.25rem;
}

ul {
    display: grid;
    gap: 8px;
    margin: 0;
    padding: 0;
    list-style: none;
}

li {
    padding-bottom: 8px;
    border-bottom: 1px solid #eee;
    color: #444;
}

.total {
    margin: 16px 0 0;
    font-weight: bold;
}

.cart + button {
    width: 100%;
    margin-top: 10px;
    padding: 10px;
    border: 0;
    border-radius: 5px;
    background: #42B883;
    color: white;
    cursor: pointer;
    font: inherit;
}

.cart + button:hover {
    background: #1b6e2b;
}

.cart + button:focus-visible {
    outline: 2px solid #42B883;
    outline-offset: 2px;
}
</style>