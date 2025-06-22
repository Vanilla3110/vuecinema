<template>
  <div class="card">
    <img :src="film.poster" :alt="film.title" width="150" />
    <h2>{{ film.title }}</h2>
    <p>{{ film.deskripsi }}</p>
    <button @click="$emit('pesanTiket', film)">Pesan Tiket</button>
  </div>
</template>

<script setup>
defineProps(['film'])
</script>
