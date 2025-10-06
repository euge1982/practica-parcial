<script setup lang="ts">

defineProps<{
  count: number,
}>()


</script>

<template>
 <div>
   <span :class="count % 2 === 0 ? 'text-green-600' : 'text-red-600'" class="font-bold text-4xl mb-5">
     {{ count }}
   </span>
 </div>
</template>

<style scoped>

</style>
