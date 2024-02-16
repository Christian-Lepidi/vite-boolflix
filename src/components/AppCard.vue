<script>
export default {
  props: { movie: Object, serie: Object },
};
</script>

<template>
  <ul class="box" v-if="movie">
    <li>
      <div class="info">Original title: {{ movie.original_title }}</div>
      <div class="info">Title: {{ movie.title }}</div>
      <div class="info">
        Language: {{ movie.original_language }}
        <img
          class="flag"
          :src="`/public/flag/${movie.original_language}-flag.jpg`"
        />
      </div>
      <div class="info">Vote average: {{ movie.vote_average }}</div>
    </li>
  </ul>

  <ul class="box" v-if="serie">
    <li>
      <div class="info">Original title: {{ serie.original_name }}</div>
      <div class="info">Title: {{ serie.name }}</div>
      <div class="info">
        Language: {{ serie.original_language }}
        <img
          class="flag"
          :src="`/public/flag/${serie.original_language}-flag.jpg`"
        />
      </div>
      <div class="info">Vote average: {{ serie.vote_average }}</div>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.box {
  max-width: 220px;
  height: 250px;
  background-color: aquamarine;
  list-style-type: none;
  text-align: center;
}

.flag {
  width: 20px;
  height: 1rem;
}
</style>
