<script setup>
import { ref, computed } from 'vue';

//Var
const msg = ref('tuto vue.js');
const fName = ref('Anthony');
const lName = ref('Cardinale');
const price = ref(100);
const discount = ref(30);

//Func
const fullName = computed(() => fName.value + " " + lName.value.toUpperCase());
const finalPrice = computed(() => price.value - (price.value * discount.value / 100));
</script>

<template>
  <main id="main">
   <h1>{{ msg }}</h1>
   <h2>Bonjour {{ fullName }}</h2>
   <h3>Prix final : {{ finalPrice }}€</h3>
  </main>
</template>

<style scoped></style>