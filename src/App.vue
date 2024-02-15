<script>
import axios from "axios";
import { store } from "./store/";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: { AppHeader, AppMain },

  methods: {
    search() {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?api_key=${store.apiKey}&language=it-IT&query=${store.text}`
        )
        .then((resp) => {
          store.movies = resp.data.results;
          console.log(store.movies);
        });
    },
    searchTv() {
      axios
        .get(
          `https://api.themoviedb.org/3/search/tv?api_key=${store.apiKey}&language=it-IT&query=${store.text}`
        )
        .then((resp) => {
          store.tvSeries = resp.data.results;
          console.log(store.tvSeries);
        });
    },
  },
};
</script>

<template>
  <app-header @search="search, searchTv"></app-header>
  <app-main></app-main>
</template>

<style lang="scss">
@use "./components/general.scss";
</style>
