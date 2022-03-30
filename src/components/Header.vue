<template>
  <header>
    <nav class="navbar navbar-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="../assets/img/logo-small.svg" alt="Spotify Logo" />
        </a>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "IndexHeader",
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
