<script>
import axios from "axios";
import { store } from "./store/";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppCard from "./components/AppCard.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: { AppHeader, AppMain, AppCard },

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
  <app-header @search="search"></app-header>
  <app-main></app-main>
  <app-card></app-card>
</template>

<style lang="scss">
@use "./components/general.scss";
</style>
