<template>
  <header>
    <nav class="navbar navbar-light">
      <div class="container-fluid px-5">
        <a class="navbar-brand" href="#">
          <img src="../assets/img/logo-small.svg" alt="Spotify Logo" />
        </a>
        <div class="d-flex">
          <select class="form-select me-2" @change="getGenre">
            <option value="all" selected>All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
          </select>
          <button
            class="btn btn-outline-success"
            type="submit"
            @click="$emit('search', filterCard)"
          >
            Search
          </button>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "IndexHeader",
  data: function () {
    return {
      filterCard: "all", // Inizialmente visualizzo le card di tutti i generi
    };
  },
  methods: {
    /* Questo metodo setta il nuovo valore per 'filterCard' */
    getGenre(v) {
      this.filterCard = v.target.options[v.target.options.selectedIndex].value;
    },
    /* getGenre(v) {
      let filterCard = v.target.options[v.target.options.selectedIndex].value;
      console.log(filterCard);
      return filterCard;
    }, */
  },
};
</script>

<style lang="scss" scoped>
/* Importo _variables.scss */
@import "../assets/scss/partials/_variables.scss";

nav.navbar {
  background-color: $primary-color;

  img {
    width: 50px;
  }
}
</style>
