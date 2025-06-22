<template>
  <div>
    <h3>Pesan Tiket untuk {{ film.title }}</h3>
    <form @submit.prevent="submitForm">
      <input v-model="nama" placeholder="Nama Pemesan" required />
      <input type="number" v-model="jumlah" placeholder="Jumlah Tiket" required />
      <select v-model="jadwal">
        <option disabled value="">Pilih Jadwal</option>
        <option>10:00</option>
        <option>14:00</option>
        <option>18:00</option>
      </select>
      <button type="submit">Kirim</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const props = defineProps(['film'])
const emit = defineEmits(['selesaiPesan'])

const nama = ref('')
const jumlah = ref(1)
const jadwal = ref('')

function submitForm() {
  console.log(`Tiket untuk ${props.film.title} oleh ${nama.value}`)
  emit('selesaiPesan')
}
</script>
