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

  <h2 class="text-center">Series</h2>
  <div class="card-container">
    <AppCard v-for="serie in store.tvSeries" :serie="serie" />
  </div>
</template>

<style lang="scss" scoped>
.info {
  color: rgb(242, 161, 11);
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
