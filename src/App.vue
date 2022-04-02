<template>
  <!-- Visualizzo al'interno della mia app tutte le sottopagine create -->
  <div id="app">
    <!-- Quando ricevo qualcosa dall'header, richiamo il metodo 'changeGenreToVisualize' -->
    <Header :genresList="genresList" @search="changeGenreToVisualize" />
    <Discs @loadedGenres="updateGenresList" :selectedGenre="genreToVisualize" />
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
      genresList: [],
      genreToVisualize: "",
    };
  },
  methods: {
    updateGenresList(genresList) {
      this.genresList = genresList;
    },
    changeGenreToVisualize(resultSearch) {
      this.genreToVisualize = resultSearch;
    },
  },
};
</script>

<style lang="scss">
/* Importo il custom style */
@import "./assets/scss/style.scss";
</style>
