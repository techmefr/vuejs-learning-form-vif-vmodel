<script setup>
import { ref } from 'vue';
import SubComp from './SubComp.vue';

const msg = ref('Hello from component')
</script>

<template>
    <h1>{{ msg }}</h1>
    <!-- Utilisation de la variable msg -->
    <SubComp> Example : {{ msg.toUpperCase() }}</SubComp>

    <!-- Utilisation du slot de l'enfant -->
    <SubComp> </SubComp>
    <SubComp/>


</template>

<style scoped>
h1 {
    color: red;
}
</style>