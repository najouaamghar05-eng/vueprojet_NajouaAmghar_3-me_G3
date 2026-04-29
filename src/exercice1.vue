<template>
  <div class="container">
    <!-- Hello World -->
    <h1>{{ message }}</h1>

    <!-- Compteur -->
    <p>Compteur : {{ compteur }}</p>
    <button @click="incrementer">Incrémenter</button>

    <!-- Objet réactif -->
    <div class="info">
      <h2>Informations :</h2>
      <p>Nom : {{ etudiant.nom }}</p>
      <p>Age : {{ etudiant.age }}</p>
      <p>Filière : {{ etudiant.filiere }}</p>
    </div>

    <!-- Toggle -->
    <p>{{ texte }}</p>
    <button @click="changerTexte">Changer le texte</button>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'

// 1. Hello World avec ref
const message = ref("Hello World")

// 2. Compteur
const compteur = ref(0)

function incrementer() {
  compteur.value++
}

// 3. Objet reactive
const etudiant = reactive({
  nom: "Najoua",
  age: 21,
  filiere: "Génie Informatique"
})

// 5. Toggle
const texte = ref("Bonjour")

function changerTexte() {
  texte.value =
    texte.value === "Bonjour"
      ? "Bonsoir"
      : "Bonjour"
}
</script>

<style>
.container {
  width: 400px;
  margin: 50px auto;
  padding: 20px;
  border-radius: 10px;
  background-color: #f2f2f2;
  text-align: center;
  font-family: Arial, sans-serif;
}

button {
  margin: 10px;
  padding: 10px 15px;
  border: none;
  background-color: #42b883;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #369f6e;
}

.info {
  margin-top: 20px;
}
</style>