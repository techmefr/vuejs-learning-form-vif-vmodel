<script setup>
const props = defineProps({
    msg: String
})
</script>

<template>
    <h1>{{ msg || "Default"}}</h1>
</template>

<style scoped>
 h1 {
     color: rebeccapurple;
 }
</style>