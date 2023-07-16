<script setup>
import { items } from "./movies.json";
import { ref } from "vue";

const movies = ref(items);
/*
 This is an Icon that you can use to represent the stars if you like
 otherwise you could just use a simple ⭐️ emoji, or * character.
*/
// import { StarIcon } from "@heroicons/vue/24/solid";
</script>

<template>
  <p class="text-4xl font-bold text-white text-center mb-4">Movie App</p>
  <div class="app">
    <div class="movie-list">
      <div class="movie-item" v-for="movie in movies" :key="movie.id">
        <img class="movie-item-image" :src="movie.image" :alt="movie.name" />
        <div class="movie-title-wrapper">
          <p class="text-black text-xl">{{ movie.name }}</p>
          <div class="flex flex-row">
            <span
              v-for="genre in movie.genres"
              :key="genre"
              class="movie-item-genre-label"
              >{{ genre }}</span
            >
          </div>
          <p class="movie-item-description">{{ movie.description }}</p>
          <div class="movie-item-rating-wrapper">
            <p class="movie-item-rating-text">Rating: ({{ movie.rating }}/5)</p>
            <span
              v-for="rating in movie.rating"
              :key="rating"
              class="movie-item-star-icon"
              >⭐
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
