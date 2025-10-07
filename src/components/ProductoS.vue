<script setup lang="ts">
import { ref } from 'vue'

interface Producto {
  id: number;
  nombre: string;
  precio: number;
}

const productos = ref<Producto[]>([
  {
    id: 1,
    nombre: "Producto 1",
    precio: 10,
  },
  {
    id: 2,
    nombre: "Producto 2",
    precio: 20,
  },
  {
    id: 3,
    nombre: "Producto 3",
    precio: 30,
  },
])

const carrito = ref<Producto[]>([])

function agregarAlCarrito(producto: Producto) {
  carrito.value.push(producto)
}
</script>

<template>
  <div v-for="producto in productos" :key="producto.id">
    <p>{{ producto.id }} - {{ producto.nombre }} - {{ producto.precio }}</p>
    <button @click="agregarAlCarrito(producto)" >Agregar al carrito</button>
  </div>
  <p v-if="carrito.length === 0">Tu carrito esta vacio</p>
  <p v-else>Carrito</p>
  <div v-for="producto in carrito" :key="producto.id">
    <p class="text-red-600 bg-gray-800">{{ producto.nombre }} - ${{ producto.precio }}</p>

  </div>
</template>

<style scoped></style>
