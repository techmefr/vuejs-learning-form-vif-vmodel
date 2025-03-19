<script setup>
import { ref, computed } from 'vue';

//var
const msg = ref('Tuto Vue.js');
const themeMode = ref(false);

// computed property
const jour = computed(() => themeMode.value);

//Func
const changeThemeMode = () => {
  themeMode.value = !themeMode.value;
};
</script>

<template>
  <main id="main" :class="!themeMode ? 'nuit' : ''">
    <h1>{{ msg }}</h1>
    <!-- Visible ou non dans le dom  -->
    <h2 v-if="themeMode == true">Jour</h2>
    <h2 v-else>Nuit</h2>
    <!-- Equivalent à display none  -->
    <h3 v-show="themeMode">Pomme</h3>
    <h3 v-show="!themeMode">Cannelle</h3>

    <button @click="changeThemeMode">Changer</button>
  </main>
</template>

<style scoped>
#main {
  background: lightblue;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.nuit {
  background: darkslategrey !important;
  color: white;
}
</style>