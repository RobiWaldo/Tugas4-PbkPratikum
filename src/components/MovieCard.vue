<template>
  <div class="movie-card" @click="toggleSelection">
    <img :src="movie.poster" alt="Movie Poster" class="movie-poster" />
    <h3 class="movie-title">{{ movie.title }}</h3>
    <div v-if="isSelected" class="selected-label">Selected</div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits, ref } from 'vue';

const props = defineProps({
  movie: {
    type: Object,
    required: true
  }
});

const emit = defineEmits(['movie-selected']);

const isSelected = ref(false);

function toggleSelection() {
  isSelected.value = !isSelected.value;
  emit('movie-selected', props.movie.title);
}
</script>

<style scoped>
.movie-card {
  position: relative;
  border: 1px solid #ccc;
  box-shadow: 0 0 10px wheat;
  border-radius: 8px;
  padding: 16px;
  margin: 8px;
  text-align: center;
  width: 200px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  background-color: rgba( 255, 255, 255, 0.1);
}

.movie-poster {
  width: 100%;
  border-radius: 8px;
}

.movie-title {
  margin-top: 12px;
  font-size: 1.2em;
}

.selected-label {
  position: absolute;
  bottom: 8px;
  left: 50%;
  transform: translateX(-50%);
  background-color: rgba(0, 0, 0, 0.8);
  color: white;
  padding: 4px 8px;
  border-radius: 4px;
}
</style>
