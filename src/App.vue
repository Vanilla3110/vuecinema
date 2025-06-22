<template>
  <div class="container">
    <h1>🎬 VueCinema</h1>
    <FilmCard 
      v-for="film in films"
      :key="film.id"
      :film="film"
      @pesanTiket="pilihFilm"
    />
    <BookingForm 
      v-if="filmDipilih" 
      :film="filmDipilih" 
      @selesaiPesan="tampilkanKonfirmasi" 
    />
    <div v-if="showConfirmation" class="konfirmasi">
      <p>Tiket berhasil dipesan! 🎟️</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import FilmCard from './components/FilmCard.vue'
import BookingForm from './components/BookingForm.vue'

const films = ref([
  { id: 1, title: 'Your Name', poster: 'https://image.tmdb.org/t/p/w200/q719jXXEzOoYaps6babgKnONONX.jpg', deskripsi: 'Anime Peak Buatan Studio Ghibli.' },
  { id: 2, title: 'Inception', poster: 'https://image.tmdb.org/t/p/w200/9gk7adHYeDvHkCSEqAvQNLV5Uge.jpg', deskripsi: 'Film sci-fi mind-blowing.' },
])

const filmDipilih = ref(null)
const showConfirmation = ref(false)

function pilihFilm(film) {
  filmDipilih.value = film
  showConfirmation.value = false
}

function tampilkanKonfirmasi() {
  showConfirmation.value = true
}
</script>
