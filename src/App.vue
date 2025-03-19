<script setup>
import { ref, computed } from 'vue';

//var
const msg = ref('Tuto Vue.js');
const themeMode = ref(false);

// computed property

//Func
const changeThemeMode = () => {
  themeMode.value = !themeMode.value;
};
</script>

<template>
  <main>
    <h1>{{ msg }}</h1>
    <h2 v-if="themeMode == true">Jour</h2>
    <h2 v-else>Nuit</h2>
    <h3 v-show="themeMode">Pomme</h3>
    <h3 v-show="!themeMode">Cannelle</h3>
    <button @click="changeThemeMode">Changer</button>
  </main>
</template>

<style scoped></style>
