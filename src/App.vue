<script setup>
import { ref, watch } from 'vue';
import HelloWorld from './components/HelloWorld.vue';

const msg = ref('Tuto Vue.js');
const question = ref('');
const answer = ref('Questions usually contain a question mark ;)');
const loading = ref(false);

// Watch for changes to the question
watch(question, async (newQuestion, oldQuestion) => {
  if (newQuestion.includes('?')) {
    loading.value = true;
    answer.value = 'Thinking...';
    try {
      const response = await fetch('https://yesno.wtf/api');
      const data = await response.json();
      answer.value = data.answer;
    } catch (err) {
      answer.value = 'Error! Could not reach the API. ' + err;
    } finally {
      loading.value = false;
    }
  }
});
</script>

<template>
  <main id="main">
    <h1>{{ msg }}</h1>
    <HelloWorld/>
    <p>Ask a yes/no question:</p>
    <input v-model="question" :disabled="loading" type="text">
    <p>{{ answer }}</p>
  </main>
</template>

<style scoped></style>