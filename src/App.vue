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
    <li>{{ movie.original_title }}</li>
  </ul>
</template>

<style lang="scss" scoped></style>
