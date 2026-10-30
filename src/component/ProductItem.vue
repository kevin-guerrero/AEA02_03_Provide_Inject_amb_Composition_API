<script setup>
 import { inject, defineProps } from 'vue';
 
 const props = defineProps(['product']);
 const cart = inject('cart');

 const addTocart = () => {
    cart.push(props.product)
    alert(`${props.product.name} afegit al carret!`)
 };

</script>

<template>
    <div class="product-item">
        <div class="product-info">
            <span class="name"> {{ product.name }} </span>
            <span class="price"> {{ product.price }} €</span>
        </div>
        <button @click="addTocart">Add to cart</button>
    </div>
</template>

<style scoped>
.product-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
    padding: 12px;
    border: 1px solid #ddd;
    border-radius: 6px;
    background: white;
}

.product-info {
    display: grid;
    gap: 4px;
    min-width: 0;
}

.name {
    font-weight: bold;
}

.price {
    color: #555;
}

button {
    flex: 0 0 auto;
    padding: 9px 12px;
    border: 0;
    border-radius: 5px;
    background: #42B883;
    color: white;
    cursor: pointer;
    font: inherit;
}

button:hover {
    background: #1b6e2b;
}

button:focus-visible {
    outline: 2px solid #42B883;
    outline-offset: 2px;
}
</style>