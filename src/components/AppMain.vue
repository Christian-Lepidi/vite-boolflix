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
  <main>
    <h2 class="text-center text-danger">Movies</h2>
    <div class="card-container">
      <AppCard v-for="movie in store.movies" :movie="movie" />
    </div>

    <h2 class="text-center text-danger mt-3">Series</h2>
    <div class="card-container">
      <AppCard v-for="serie in store.tvSeries" :serie="serie" />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  min-height: 675px;
  background-color: rgb(75, 75, 75);
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
