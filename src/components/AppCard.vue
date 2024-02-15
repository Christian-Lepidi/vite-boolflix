<script>
export default {
  props: { movie: Object },
};
</script>

<template>
  <ul class="box">
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
  <ul class="box">
    <li>
      <span class="info">Original title:</span> {{ serie.original_name }}
      <span class="info">Title:</span> {{ serie.name }}
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
.box {
  width: 140px;
  height: 170px;
  background-color: aquamarine;
}

.flag {
  width: 20px;
  height: 1rem;
}
</style>
