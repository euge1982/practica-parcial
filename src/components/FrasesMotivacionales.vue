<script setup lang="ts">

import { ref } from 'vue'

const frases: string[] = [
  'frase 1',
  'frase 2',
  'frase 3',
  'frase 4',
  'frase 5'
]

const fraseSeleccionada = ref<string | null>(null)

function seleccionarFrase(frase: string): void {
  fraseSeleccionada.value = frase
}

</script>

<template>
  <div >
    <button v-for="frase in frases" :key="frase"
            @click="seleccionarFrase(frase)"
            :class='frase===fraseSeleccionada ? "bg-green-500 text-white p-4 rounded" : "bg-emerald-800 text-white p-4 rounded"'>
            {{ frase }}
    </button>
    <div>
      <p v-if="fraseSeleccionada !== null">Frase seleccionada: {{ fraseSeleccionada }}</p>
      <p v-else>Selecciona una frase</p>
    </div>
  </div>

</template>

<style scoped>
</style>
