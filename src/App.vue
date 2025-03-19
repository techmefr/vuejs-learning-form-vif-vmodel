<script setup>
import { ref } from 'vue';

//Var
const msg = ref('Tuto Vue.Js')
const items = ref(['Item 1', 'Item 2', 'Item 3'])
let id = 0

const goodItems = ref([
  { id: id++, text: 'Olivier' },
  { id: id++, text: 'Tom' },
  { id: id++, text: 'Marc' }
])

const newCharacter = ref('');
const characters = ref([
  { id: id++, text: 'Dark' },
  { id: id++, text: 'Luke' }
])

//Func
const addCharacter = () => {
  if (newCharacter.value.trim()) {
    characters.value.push({ id: id++, text: newCharacter.value })
    newCharacter.value = ''
  }
}

const removeCharacter = (character) => {
  characters.value = characters.value.filter((item) => item.id !== character.id)
}
</script>

<template>
  <main id="main">
    <h1>{{ msg }}</h1>
    <ul>
      <li>Toto</li>
      <li>Titi</li>
    </ul>

    <ul>
      <li v-for="item in items" :key="item">{{ item }}</li>
    </ul>

    <ul>
      <li v-for="goodItem in goodItems" :key="goodItem.id">{{ goodItem.text }}</li>
    </ul>

    <div>
      <h2>Personnages</h2>
      <ul>
        <li v-for="character in characters" :key="character.id">
          {{ character.text }} 
          <button @click="removeCharacter(character)">X</button>
        </li>
      </ul>
      <input type="text" v-model="newCharacter">
      <button @click="addCharacter">Add character</button>
    </div>
  </main>
</template>

<style scoped></style>