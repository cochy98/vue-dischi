<template>
  <!-- Single card -->
  <div class="col">
    <div class="card h-100 text-center">
      <img class="card-img-top" :src="discInfo.poster" :alt="discInfo.title" />
      <div class="card-body">
        <h3 class="card-title">{{ discInfo.title }}</h3>
      </div>
      <div class="card-footer">
        <p class="card-text m-0">{{ discInfo.author }}</p>
        <p class="card-text">{{ discInfo.year }}</p>
      </div>
    </div>
  </div>
  <!-- /Single card -->
</template>

<script>
export default {
  name: "SingleDisc",
  props: {
    discInfo: Object,
  },
};
</script>

<style lang="scss" scoped>
/* Importo _variables.scss */
@import "../assets/scss/partials/_variables.scss";

div.card {
  background-color: $primary-color;
  border: none;
  border-radius: 0;

  img.card-img-top {
    padding: 1.1rem;
  }

  h3.card-title {
    text-transform: uppercase;
    color: white;
  }

  .card-footer {
    padding: 0.5rem 1rem;
    background-color: transparent;
    border-top: none;
    padding: 2rem;

    p.card-text {
      color: $description-color;
    }
  }
}
</style>
