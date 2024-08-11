<template>
  <div class="css">
    <h2>Addition</h2>
    <label for="int">Entrez le premier nombre entier : </label>
    <input type="number" name="entiera" id="int" v-model="a">

    <label for="int2">Entrez le deuxième nombre entier : </label>
    <input type="number" name="entierb" id="int2" v-model="b">

    <button type="button" @click="addition">Calculer</button>

    <p>Le resultat de votre calcul est : {{ resultat }}</p>
  </div>

</template>

<script setup>
import { ref } from 'vue'

const a = ref('')
const b = ref('')
let resultat = ref(0)
let message

function addition() {
  try {
    if (!a.value || !b.value) {
      throw new Error("Entrez un nombre entier")
    }
    resultat.value = ref(a.value + b.value)
    return resultat

  } catch (e) {
    console.log(e)
    message = e.message
    return message
  }
}

</script>


<style scoped></style>
