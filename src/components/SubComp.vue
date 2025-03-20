<script setup>
const props = defineProps({
    msg: {
        type: String,
        required: false,
        default: "Titi"
    },
    color: {
        type: String,
        required: false
    }
});

// Définit ce qu'on peut émettre au parent
const emit = defineEmits(['compMsg'])

const clickHandler = () => {
    console.log("Click" + " " + props.msg)
    emit('compMsg', props.msg)
}
</script>

<template>
    <h2 :class="color">{{ msg || "Default" }}</h2>
    <button @click="clickHandler">Click</button>
</template>

<style scoped>
h1 {
    color: rebeccapurple;
}

.red {
    color: red !important;
}

.blue {
    color: blue !important;
}
</style>
