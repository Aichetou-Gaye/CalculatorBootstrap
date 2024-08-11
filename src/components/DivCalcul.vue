<template>
  <div class="css">
    <h2>Division</h2>
    <label for="int">Entrez le premier nombre entier : </label>
    <input type="number" name="entiera" id="int" v-model="a">

    <label for="int2">Entrez le deuxième nombre entier : </label>
    <input type="number" name="entierb" id="int2" v-model="b">

    <button type="button" @click="division">Calculer</button>

    <p>Le resultat de votre calcul est : {{ resultat }}</p>
  </div>

</template>

<script setup>
import { ref } from 'vue'

const a = ref('')
const b = ref('')
let resultat = ref(0)
let message

function division() {
  try {
    if ((!a.value || !b.value) || b.value === 0) {
      throw new Error("Entrez un nombre entier supérieur 0")
    } 
    resultat.value = ref(a.value / b.value)
    return resultat

  } catch (e) {
    console.log(e)
    message = e.message
    return message
  }
}

</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat+Alternates:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Montserrat:ital,wght@0,100..900;1,100..900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
.css {
  margin: auto;
  display: flex;
  flex-direction: column;
  background-color: #5ca5bb;
  border-radius: 6px;
  width: 600px;
  padding: 30px;
}
label, button, input, p, h3, h2 {
  font-family: Montserrat;
  font-size: 1em;
  font-weight: 600;
  color: #ffffff;
}
h2{
  font-size: 1.2em;
  text-align: center;
}
input, button {
  outline: none;
  border-radius: 5px;
  border: none;
  margin-bottom: 20px;
}
button {
  background-color: #033f52;
  height: 30px;
}
input {
  color: #033f52;
}
</style>
