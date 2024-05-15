<template>
  <div class="movie-list">
    <MovieCard v-for="movie in movies" :key="movie.id" :movie="movie" @movie-selected="handleMovieSelected(movie.title)" />
  </div>
</template>

<script setup>
import { defineProps, ref } from 'vue';
import MovieCard from './MovieCard.vue';

const props = defineProps({
  movies: {
    type: Array,
    required: true
  }
});

const selectedMovies = ref([]);

function handleMovieSelected(movieTitle) {
  if (selectedMovies.value.includes(movieTitle)) {
    selectedMovies.value = selectedMovies.value.filter(title => title !== movieTitle);
  } else {
    selectedMovies.value.push(movieTitle);
  }
}
</script>

<style scoped>
.movie-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
