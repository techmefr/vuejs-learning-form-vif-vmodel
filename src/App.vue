<script setup>
import { ref, watch } from 'vue';

const msg = ref('Tuto Vue.js');
const x = ref(0);
const dbg = ref('');
const locked= ref(false)

watch(x, (newX, oldX) => {
  dbg.value = 'x = ' + newX+ " | old = "+oldX;
  if (newX>5){
    locked.value = true
    // on ne peut plus modifier la valeur si celle-ci dépasse 5
  }
});
</script>

<template>
  <main id="main">
    <h1>{{ msg }}</h1>
    <p>{{ dbg }}</p>
    <input :disabled="locked" type="number" v-model="x">
  </main>
</template>

<style scoped></style>