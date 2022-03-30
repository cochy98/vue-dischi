<template>
  <!-- Visualizzo al'interno della mia app tutte le sottopagine create -->
  <div id="app">
    <Header />
    <Discs />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Discs from "./components/Discs.vue";

export default {
  name: "App",
  components: {
    Header,
    Discs,
  },
};
</script>

<style lang="scss">
/* Importo il custom style */
@import "./assets/scss/style.scss";
</style>
