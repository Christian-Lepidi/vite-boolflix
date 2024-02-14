<script>
import axios from "axios";

export default {
  data() {
    return {
      text: "",
      movies: [],
    };
  },

  methods: {
    search() {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?query=${this.text}&api_key=0b300dc176f15d44c67f58d11a7ba493`
        )
        .then((resp) => {
          this.movies = resp.data.results;
          console.log(this.movies);
        });
    },
  },
};
</script>

<template>
  <input
    v-model="text"
    class="form-control me-2"
    type="search"
    placeholder="Search"
    aria-label="Search"
  />
  <button class="btn btn-outline-success" type="submit" @click="search()">
    Search
  </button>
  <ul v-for="movie in movies">
    <li>
      <span class="info">Original title:</span> {{ movie.original_title }}
      <span class="info">Title:</span> {{ movie.title }}
      <span class="info">Language:</span>
      {{ movie.original_language }} <span class="info">Vote average:</span>
      {{ movie.vote_average }}
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.info {
  color: rgb(213, 31, 31);
}
</style>
