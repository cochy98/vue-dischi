<template>
  <!-- Visualizzo al'interno della mia app tutte le sottopagine create -->
  <div id="app">
    <!-- Quando ricevo qualcosa dall'header, richiamo il metodo 'changeGengeToVisualize' -->
    <Header @search="changeGengeToVisualize" />
    <Discs :visualize="genreToVisualize" />
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
  data: function () {
    return {
      genreToVisualize: "0",
    };
  },
  methods: {
    changeGengeToVisualize(resultSearch) {
      this.genreToVisualize = resultSearch;
      //console.log(`Risposta della ricerca: ${resultSearch}`);
    },
  },
};
</script>

<style lang="scss">
/* Importo il custom style */
@import "./assets/scss/style.scss";
</style>
