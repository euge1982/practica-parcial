<script setup lang="ts">
import { ref } from 'vue';
import MostrarContador from './MostrarContador.vue';

const count = ref(0);

function decrementar (): number {
  return count.value--;
}

function incrementar (): number {
  return count.value++;
}

</script>

<template>
  <div class="text-xl text-center flex flex-col items-center justify-center md:text-2xl md:font-bold lg:text-3xl gap-10">
    <h2>
      <MostrarContador :count="count" />
    </h2>
    <div class="flex items-center justify-center mt-4 gap-6">
      <button @click="decrementar()" class="bg-red-500 rounded px-4 py-2 hover:bg-red-600 hover:text-white hover:cursor-pointer mr-4">
        DECREMENTAR
      </button>
      <button @click="incrementar()" class="bg-green-500 rounded px-4 py-2 hover:bg-green-600 hover:text-white hover:cursor-pointer">
        INCREMENTAR
      </button>
    </div>
  </div>
</template>

<style scoped>

</style>
