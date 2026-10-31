<script setup>
    import { defineProps } from 'vue';

    const props = defineProps(['product']);
</script>

<template>
    <li>
        {{ product.name }} - {{ product.price }} €
    </li>
</template>