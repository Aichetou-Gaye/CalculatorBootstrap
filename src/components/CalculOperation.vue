<template>
  <div class="container my-5">
    <input type="radio" class="btn-check" name="options-outlined" id="success-1" value="addition" v-model="select">
    <label class="btn btn-outline-success" for="success-1">Addition</label>

    <input type="radio" class="btn-check" name="options-outlined" id="success-2" value="soustraction" v-model="select">
    <label class="btn btn-outline-success" for="success-2">Soustraction</label>

    <input type="radio" class="btn-check" name="options-outlined" id="success-3" value="multiplication"
      v-model="select">
    <label class="btn btn-outline-success" for="success-3">Multiplication</label>

    <input type="radio" class="btn-check" name="options-outlined" id="success-4" value="division" v-model="select">
    <label class="btn btn-outline-success" for="success-4">Division</label>
  </div>

  <div v-if="select !== null">
    <div class="container-fluid">
      <h1>Veuillez entrez les entiers </h1>
      <div class="form-floating mb-3">
        <input type="number" class="form-control" id="floatingInput" placeholder="valeur 1" v-model="value1">
        <label for="floatingInput">Première Valeur</label>
      </div>
      <div class="form-floating">
        <input type="number" class="form-control" id="floatingPassword" placeholder="valeur 2" v-model="value2">
        <label for="floatingPassword">Deuxième Valeur</label>
      </div>
      <div class="btn-group my-3" role="group" aria-label="Basic mixed styles example">
        <button type="button" class="btn btn-success" @click="calculer">Calculer</button>
        <button type="button" class="btn btn-success" @click="supprimer">Supprimer</button>
      </div>
      <p>Le resultat est : {{ resultat }}</p>
      <p class="text-danger">{{ errorCode }}</p>
    </div>


  </div>

</template>

<script setup>
import { ref } from 'vue'

const value1 = ref(0)
const value2 = ref(0)
let select = ref(null)
const resultat = ref(null)
const errorCode = ref('')

function calculer() {
  try{
    if (!value1.value || !value2.value) {
      errorCode.value =  ref("Seul les nombres entiers sont autorisés")
      throw new Error("Veuillez saisir des nombres entiers")
    }
    switch (select.value) {
      case 'addition' :
        resultat.value = value1.value + value2.value
      break
      case 'soustraction' :
        resultat.value = value1.value - value2.value
      break
      case 'multiplication' :
        resultat.value = value1.value * value2.value
      break
      case 'division' :
        if(value2.value === 0) {
          errorCode.value =  ref("la division par zero est impossible")
          throw new Error('la division par zero est impossible')
        }
        resultat.value = value1.value / value2.value
      break
      default :
        resultat.value = null
      break
    }
    
  }catch(error) {
    console.log(error.message)
  }
}

function supprimer() {
  select.value = null
}

</script>

