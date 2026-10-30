<script setup>
import { inject } from 'vue';
import ProductItem from './ProductItem.vue';

const products = inject('products');
</script>

<template>
    <div class="category-list">
        <h2>Productes</h2>
        <div class="productes">
            <ProductItem 
            v-for="p in products"
            :key="p.name"
            :product="p"
            /> 
        </div>
    </div>
</template>

<style scoped>
.category-list {
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    background: white;
}

h2 {
    margin: 0 0 16px;
    font-size: 1.25rem;
}

.productes {
    display: grid;
    gap: 10px;
}
</style>