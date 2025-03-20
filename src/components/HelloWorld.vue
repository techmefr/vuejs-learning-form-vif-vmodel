<script setup>
import { ref } from 'vue';

const msg = ref('Hello from component')

</script>

<template>
    <h1>{{ msg }}</h1>
</template>

<style scoped>
h1 {
    color: red;
}</style>