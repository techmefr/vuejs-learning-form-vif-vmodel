# Vue.js - Apprentissage des directives v-if, v-show et v-model

![Vue.js Logo](https://vuejs.org/images/logo.png)

Un projet didactique pour comprendre les concepts fondamentaux de Vue.js, notamment l'utilisation des directives conditionnelles et la liaison de données bidirectionnelle.

## 📝 Description

Ce projet est conçu comme un tutoriel interactif permettant d'explorer les fonctionnalités essentielles de Vue.js. Il présente un exemple simple de basculement entre les thèmes "Jour" et "Nuit", démontrant comment les directives conditionnelles peuvent modifier dynamiquement l'interface utilisateur.

### Fonctionnalités démontrées

- **v-if / v-else** : Affichage/masquage conditionnel avec retrait complet du DOM
- **v-show** : Affichage/masquage conditionnel avec CSS (`display: none`)
- **Événements** : Gestion des événements avec `@click`
- **Variables réactives** : Utilisation de `ref()` pour créer des données réactives
- **Import de Propriétés calculées** : Import de `computed()` (bien que non utilisé dans le code actuel)

## 🚀 Installation

1. Clonez le dépôt :
```bash
git clone https://github.com/techmefr/vuejs-learning-form-vif-vmodel.git
cd vuejs-learning-form-vif-vmodel
```

2. Installez les dépendances :
```bash
npm install
```

## 💻 Utilisation

1. Démarrez le serveur de développement :
```bash
npm run dev
```

2. Ouvrez votre navigateur à l'adresse [http://localhost:5173](http://localhost:8080)

3. Interagissez avec l'interface pour voir les directives en action

## 🧩 Structure du code

### Composant principal

```vue
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

<style scoped>
/* Vos styles CSS ici */
</style>
```

## 📚 Explications détaillées

### Directives utilisées

| Directive | Description | Exemple dans le code |
|-----------|-------------|---------------------|
| `v-if` | Conditionnellement ajoute/supprime l'élément du DOM | `<h2 v-if="themeMode == true">Jour</h2>` |
| `v-else` | Alternative pour `v-if` | `<h2 v-else>Nuit</h2>` |
| `v-show` | Conditionnellement affiche/masque avec CSS | `<h3 v-show="themeMode">Pomme</h3>` |
| `@click` | Écoute les événements de clic | `<button @click="changeThemeMode">Changer</button>` |

### Différence entre v-if et v-show

- **v-if** : Rend ou supprime complètement l'élément du DOM. Utiliser pour les conditions qui changent rarement.
- **v-show** : Utilise `display: none` pour cacher l'élément. Meilleur pour les bascules fréquentes.

## 🛠️ Possibilités d'extension

Ce projet peut être enrichi avec :

- Ajout de la directive `v-model` pour les formulaires
- Implémentation de transitions lors des changements d'état
- Utilisation de composants enfants et communication entre composants
- Ajout d'un état persistant avec localStorage

## 📄 Licence

[MIT](https://opensource.org/licenses/MIT)
