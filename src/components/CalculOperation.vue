<template>
  <div>
    <Addition />
    <Soustraction />
    <Multiplication />
    <Division />
  </div>

  <!-- <div>
    <b-form-group label="Inline radios (default)" v-slot="{ ariaDescribedby }">
      <b-form-radio-group v-model="selected" :options="options" :aria-describedby="ariaDescribedby"
        name="radio-inline"></b-form-radio-group>
    </b-form-group>
  </div> -->


</template>

<script setup>

import Addition from './AddCalcul.vue'
import Soustraction from './DeleteCalcul.vue'
import Multiplication from './MultiplyCalcul.vue'
import Division from './DivCalcul.vue'

</script>


<style scoped>
</style>

<!-- <div class="dropdown">
  <a class="btn btn-secondary dropdown-toggle" href="#" role="button" id="dropdownMenuLink" data-bs-toggle="dropdown" aria-expanded="false">
    Operation
  </a>

  <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink">
    <Addition></Addition>
    <Soustraction></Soustraction>
    <Division></Division>
    <Multiplication></Multiplication>
    <li ><a class="dropdown-item" href="./AddCalcul.vue">Addition</a></li>
    <li><a class="dropdown-item" href="./DeleteCalcul.vue">Soustraction</a></li>
    <li><a class="dropdown-item" href="./MultiplyCalcul.vue">Multiplication</a></li>
    <li><a class="dropdown-item" href="./DivCalcul.vue">Division</a></li>
  </ul>
</div> -->