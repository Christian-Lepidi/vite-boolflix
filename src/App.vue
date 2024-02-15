<script>
import axios from "axios";
import { store } from "./store/";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: { AppHeader, AppMain },
};
</script>

<template>
  <app-header></app-header>
  <app-main></app-main>
</template>

<style lang="scss">
@use "./components/general.scss";
</style>
