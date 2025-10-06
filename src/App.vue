<script setup lang="ts">
import { ref } from 'vue';

const mostrar = ref(false);
</script>

<template>
  <div>
    <h1>EJERCICIO N° 4</h1>

    <button @click="if (mostrar) mostrar=false; else mostrar=true">Abrir menu</button>
    <div v-show="mostrar" :class="mostrar ? 'transition transform duration-300 translate-x-0' : 'transition transform duration-300 -translate-x-full'">
      <ul>
        <li><a href="#">Enlace 1</a></li>
        <li><a href="#">Enlace 2</a></li>
        <li><a href="#">Enlace 3</a></li>
      </ul>

    </div>
  </div>


</template>

<style scoped></style>
