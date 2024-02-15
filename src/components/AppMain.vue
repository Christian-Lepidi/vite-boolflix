<script>
import { store } from "../store/index.js";
import AppCard from "../components/AppCard.vue";
export default {
  data() {
    return {
      store,
    };
  },
  components: { AppCard },
};
</script>

<template>
  <h2>Movies</h2>
  <AppCard v-for="movie in store.movies" :movie="movie" />
  <AppCard v-for="serie in store.tvSeries" :serie="serie" />

  <h2>Series</h2>
</template>

<style lang="scss" scoped>
.info {
  color: rgb(242, 161, 11);
}
</style>
