<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
      text: "",
    };
  },
  methods: {
    search() {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?query=${this.text}&api_key=${store.apiKey}`
        )
        .then((resp) => {
          store.movies = resp.data.results;
          console.log(store.movies);
        });
    },
  },
};
</script>

<template>
  <div class="d-flex">
    <input
      v-model="text"
      class="form-control me-2"
      type="search"
      placeholder="Search"
      aria-label="Search"
    />
    <button type="button" class="btn btn-danger" @click="search()">
      Search
    </button>
  </div>
</template>

<style lang="scss" scoped></style>
