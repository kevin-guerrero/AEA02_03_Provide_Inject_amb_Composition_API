<script setup>
import { provide, reactive } from "vue";
import CategoryList from "./component/CategoryList.vue";
import Cart from "./component/Cart.vue";

const cart = reactive([]);

const products = [
  { name: "Auriculars Wireless 🎧", price: 50 },
  { name: "Smartwatch ⌚", price: 120 },
  { name: "Teclat Mecànic ⌨️", price: 80 },
  { name: "Altaveu Bluetooth 🔊", price: 60 },
];

provide("cart", cart);
provide("products", products);
</script>

<template>
  <div class="app-container">
    <h1>Botiga de gadgets</h1>
    <div class="content">
      <CategoryList></CategoryList>
      <Cart></Cart>
    </div>
  </div>
</template>

<style scoped></style>