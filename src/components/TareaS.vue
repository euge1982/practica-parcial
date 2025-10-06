<script setup lang="ts">
import TareasItem from './TareasItem.vue';
import { ref } from 'vue';

const tareas = ref<string[]>([])

const nuevaTarea = ref("")

function agregarTarea(){
  if (nuevaTarea.value !== ''){
    tareas.value.push(nuevaTarea.value);
    nuevaTarea.value = ''
  }
}

</script>

<template>
  <div class="text-center p-8 mt-20">
    <input type="text" id="tarea" v-model="nuevaTarea" placeholder="Nueva Tarea">
    <button @click="agregarTarea">Agregar Tarea</button>
    <p v-if="tareas.length === 0">No hay tareas aun</p>
    <div v-else>

      <li v-for="tarea in tareas" :key="tarea" class="mt-20">
        <TareasItem :tarea="tarea"/>
      </li>

    </div>

  </div>
</template>
