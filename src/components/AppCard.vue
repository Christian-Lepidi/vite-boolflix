<script>
export default {
  props: { movie: Object, serie: Object },
};
</script>

<template>
  <ul class="box" v-if="movie">
    <li>
      <div class="back-image">
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
      </div>
      <img
        class="poster front-image"
        :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`"
        alt=""
      />
    </li>
  </ul>

  <ul class="box" v-if="serie">
    <li>
      <div class="back-image">
        <div>Original title: {{ serie.original_name }}</div>
        <div>Title: {{ serie.name }}</div>
        <div>
          Language: {{ serie.original_language }}
          <img
            class="flag"
            :src="`/public/flag/${serie.original_language}-flag.jpg`"
          />
        </div>
        <div>Vote average: Math.ceil({{ serie.vote_average }} / 2)</div>
      </div>
      <img
        class="poster front-image"
        :src="`https://image.tmdb.org/t/p/w342/${serie.poster_path}`"
        alt=""
      />
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.box {
  max-width: 220px;
  height: 250px;
  list-style-type: none;
  text-align: center;
}

.flag {
  width: 20px;
  height: 1rem;
}

.poster {
  max-width: 100%;
}

.front-image {
  display: block;
}

.back-image {
  display: none;
}

.box:hover .front-image {
  display: none;
}

.box:hover .back-image {
  display: block;
}
</style>
