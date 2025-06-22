<!-- src/components/FilmCard.vue -->
<template>
  <div class="film-card">
    <h2>{{ film.title }}</h2>
    <button @click="$emit('pesan')">Pesan Tiket</button>
  </div>
</template>

<script setup>
const props = defineProps(['film'])
</script>
