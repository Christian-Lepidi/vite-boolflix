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
  <h2 class="text-center">Movies</h2>
  <div class="card-container">
    <AppCard v-for="movie in store.movies" :movie="movie" />
  </div>

  <h2 class="text-center mt-3">Series</h2>
  <div class="card-container">
    <AppCard v-for="serie in store.tvSeries" :serie="serie" />
  </div>
</template>

<style lang="scss" scoped>
.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
