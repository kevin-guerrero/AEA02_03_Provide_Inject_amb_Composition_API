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

<style scoped>
:global(*) {
  box-sizing: border-box;
}

:global(body) {
  min-width: 320px;
  min-height: 100vh;
  margin: 0;
  background: #f5f7f5;
  color: #222;
  font-family: Arial, sans-serif;
}

.app-container {
  width: min(1000px, calc(100% - 32px));
  margin: 0 auto;
  padding: 40px 0;
}

h1 {
  margin: 0 0 28px;
  font-size: 2rem;
  text-align: center;
}

.content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  align-items: start;
  gap: 20px;
}

@media (max-width: 650px) {
  .content {
    grid-template-columns: 1fr;
  }
}
</style>