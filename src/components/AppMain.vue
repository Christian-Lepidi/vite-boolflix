<script>
import { store } from "../store/index.js";

export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <ul v-for="movie in store.movies">
    <li>
      <span class="info">Original title:</span> {{ movie.original_title }}
      <span class="info">Title:</span> {{ movie.title }}
      <span class="info">Language:</span>
      {{ movie.original_language
      }}<img
        class="flag"
        :src="`/public/flag/${movie.original_language}-flag.jpg`"
      />
      <span class="info">Vote average:</span>
      {{ movie.vote_average }}
    </li>
  </ul>
  <ul v-for="serie in tvSeries">
    <li>
      <span class="info">Original title:</span> {{ serie.original_title }}
      <span class="info">Title:</span> {{ serie.title }}
      <span class="info">Language:</span>
      {{ serie.original_language
      }}<img
        class="flag"
        :src="`/public/flag/${serie.original_language}-flag.jpg`"
      />
      <span class="info">Vote average:</span>
      {{ serie.vote_average }}
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.info {
  color: rgb(242, 161, 11);
}

.flag {
  width: 20px;
  height: 1rem;
}
</style>
