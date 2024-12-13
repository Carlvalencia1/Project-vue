<template>
  <button @click="decremento">-</button>
  <span :class="miColor">{{ contador }}</span>
  <button @click="incremento">+</button>
  <div v-if="contador<0">Escribe una cantidad mayor a 0</div>
  <div v-else-if="contador>=5">Escribe una cantidad menor a 5</div>
  <div v-show="comprobacion">No esta permitido el 0</div>
  <img :src="image" alt="">
</template>

<script setup>
import {ref, computed } from "vue";
import {valores} from "./datos.js"

// Declaracion de variables
const image ="valores.web"
const miColor =ref("azul")
const contador =ref (0);
const decremento =()=>{
  contador.value--;
  if (contador.value<0) {
    miColor.value="rojo"
  } 
}

const incremento =()=>{
  contador.value++;
  if (contador.value > (5) ) {
    miColor.value="verde"
  }
}

const comprobacion=computed(()=>{
  return contador.value===0
})
</script>


<style scoped>
span {
 padding: 5px;
}
.rojo{
  color: red;
}

.verde{
  color: green;
}
</style>