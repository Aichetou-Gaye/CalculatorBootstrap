<template>
  <div class="calc">
    <div>
      <label for="add">Addition</label>
      <input id="add" type="radio" v-model="Addition">
    </div>

    <div>
      <label for="del">Soustraction</label>
      <input id="del" type="radio" v-model="Soustraction">
    </div>

    <div>
      <label for="mul">Multiplication</label>
      <input id="mul" type="radio" v-model="Multiplication">
    </div>

    <div>
      <label for="div">Division</label>
      <input id="div" type="radio" v-model="Division">
    </div>


  </div>
</template>

<script setup>

import Addition from './AddCalcul.vue'
import Soustraction from './DeleteCalcul.vue'
import Multiplication from './MultiplyCalcul.vue'
import Division from './DivCalcul.vue'

</script>


<style scoped>
div {
  display: flex;
  justify-content: space-between;
}
.calc {
  display: flex;
  flex-direction: column;
  background-color: #0123b9;
  width: 30%;
  margin: 60px auto;
  padding: 10px 30px;
  border-radius: 5px;
}
</style>
