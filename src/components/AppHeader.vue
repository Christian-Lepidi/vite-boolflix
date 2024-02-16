<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  emits: ["search"],
};
</script>

<template>
  <header class="d-flex justify-content-between">
    <div class="title-box d-flex align-items-center">
      <h1 class="title-name text-danger">BOOLFLIX</h1>
    </div>
    <div class="search-bar d-flex align-items-center">
      <input
        v-model="store.text"
        class="input-bar form-control me-2"
        type="search"
        placeholder="Search"
        aria-label="Search"
      />
      <button
        type="button"
        class="input-bar btn btn-danger"
        @click="$emit('search')"
      >
        Search
      </button>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  width: 100%;
  height: 90px;
  background-color: rgb(23, 22, 22);
}

.title-box {
  width: 30%;
  height: 100%;
}

.search-bar {
  width: 30%;
  height: 100%;
}

.input-bar {
  height: 40%;
}
</style>
