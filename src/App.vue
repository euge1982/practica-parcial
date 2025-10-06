<script setup lang="ts">
const colores:string[]=["red","green","blue","yellow","orange","pink"]
</script>

<template>
  <div>
    <h1>EJERCICIO N° 3</h1>
    <div v-for="color in colores" :key="color" :style="{'background-color':color}">

    </div>

  </div>



</template>

<style scoped></style>
