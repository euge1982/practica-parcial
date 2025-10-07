<script setup lang="ts">

import { ref } from 'vue'

const email = ref('')
const nombre = ref('')
const mensaje = ref('')

function enviar () {
  if (email.value && nombre.value) {
    mensaje.value = 'Registro exitoso'
  }
  else {
    mensaje.value = 'Completar todos los campos'
  }

  nombre.value = ''
  email.value = ''
}
</script>

<template>
  <div>
    <input type="text" v-model="nombre" placeholder="Escribe tu nombre">
    <input type="text" v-model="email" placeholder="Escribe tu email">
    <button @click="enviar">Enviar</button>
    <p v-show="mensaje" :class="mensaje === 'Registro exitoso'?'text-green-600':'text-red-600'">{{ mensaje }}</p>
    
  </div>
</template>

<style scoped></style>
