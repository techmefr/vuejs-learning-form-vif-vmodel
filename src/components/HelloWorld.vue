<script setup>
import { ref } from 'vue';
import SubComp from './SubComp.vue';

const msg = ref('Hello from component')

</script>

<template>
    <h1>{{ msg }}</h1>
<SubComp/>
<SubComp msg="Toto"/>
<!-- on peut passer une variable dans la props -->
<SubComp :msg="msg"/>

</template>

<style scoped>
h1 {
    color: red;
}</style>