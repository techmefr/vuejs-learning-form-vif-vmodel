<script setup>
import { ref } from 'vue';
import SubComp from './SubComp.vue';

const msg = ref('Hello from component')
const childMsg = ref('No msg')
</script>

<template>
    <h1>{{ msg }}</h1>
    <h3>{{ childMsg }}</h3>
<SubComp @compMsg="(msg)=> childMsg=msg" msg="Test msg"/>
<SubComp msg="Toto"/>
<SubComp :msg="msg" color="red"/>

</template>

<style scoped>
h1 {
    color: red;
}</style>