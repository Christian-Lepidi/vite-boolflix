<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  emits: ["search", "searchTv"],
};
</script>

<template>
  <div class="d-flex">
    <input
      v-model="store.text"
      class="form-control me-2"
      type="search"
      placeholder="Search"
      aria-label="Search"
    />
    <button
      type="button"
      class="btn btn-danger"
      @click="$emit('search', 'searchTv')"
    >
      Search
    </button>
  </div>
</template>

<style lang="scss" scoped></style>
