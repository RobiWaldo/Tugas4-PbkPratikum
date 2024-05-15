<template>
  <div id="app">
    <h1>Saksikan Film Kesukan Anda</h1>
    <MovieList :movies="movies" @movie-selected="showSelectedMovie" />
    <div v-if="selectedMovie" class="selected-movie">
      <h2>Selected Movie: {{ selectedMovie }}</h2>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import MovieList from './components/MovieList.vue';

const movies = ref([
  { id: 1, title: 'The Batman', poster: 'https://m.media-amazon.com/images/M/MV5BM2MyNTAwZGEtNTAxNC00ODVjLTgzZjUtYmU0YjAzNmQyZDEwXkEyXkFqcGdeQXVyNDc2NTg3NzA@._V1_.jpg' },
  { id: 2, title: 'Spider-Man: No Way Home', poster: 'https://image.tmdb.org/t/p/w200/1g0dhYtq4irTY1GPXvft6k4YLjm.jpg' },
  { id: 3, title: 'Doctor Strange in the Multiverse of Madness', poster: 'https://image.tmdb.org/t/p/w200/9Gtg2DzBhmYamXBS1hKAhiwbBKS.jpg' },
  { id: 4, title: 'Thor: Love and Thunder', poster: 'https://image.tmdb.org/t/p/w200/pIkRyD18kl4FhoCNQuWxWu5cBLM.jpg' },
  { id: 5, title: 'Jurassic World Dominion', poster: 'https://image.tmdb.org/t/p/w200/kAVRgw7GgK1CfYEJq8ME6EvRIgU.jpg' },
  { id: 6, title: 'Top Gun: Maverick', poster: 'https://image.tmdb.org/t/p/w200/62HCnUTziyWcpDaBO2i1DX17ljH.jpg' },
  { id: 7, title: 'Avatar: The Way of Water', poster: 'https://lumiere-a.akamaihd.net/v1/images/p_disneyplusoriginals_avatar_thewayofwater_poster_rebra_fa08636d.jpeg' },
  { id: 8, title: 'Black Panther: Wakanda Forever', poster: 'https://jabarekspres.com/wp-content/uploads/2022/11/2021a99439876fab45f125d53b2d5d01.jpg' }
]);

const selectedMovie = ref(null);

function showSelectedMovie(movieTitle) {
  selectedMovie.value = movieTitle;
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Sedan+SC&display=swap');

body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: black;
  color: #333;
}

h1 {
  text-align: center;
  margin-top: 20px;
  text-shadow: 0 0 3px wheat;
  font-family: "Sedan SC", serif;
}

#app {
  padding: 20px;
}

.selected-movie {
  text-align: center;
  margin-top: 20px;
  color: wheat;
  text-shadow: 0 0 3px wheat;
}
</style>
