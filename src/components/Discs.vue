<template>
  <main>
    <div class="container">
      <div class="row row-cols-1 row-cols-md-3 row-cols-lg-5 g-4 py-5">
        <!-- Ciclo sulla pagina che consente di generare una singola card -->
        <SingleDisc
          v-for="(element, index) in filteredDiscList"
          :key="index"
          :discInfo="element"
        />
      </div>
    </div>
  </main>
</template>

<script>
// Inizializziamo la libreria 'axios' come variabile axios
import axios from "axios";
import SingleDisc from "./DiscCard.vue";

export default {
  name: "IndexMain",
  components: {
    SingleDisc,
  },
  created() {
    this.getApiList();
  },

  data() {
    return {
      discList: [],
    };
  },
  props: ["selectedGenre"],
  computed: {
    filteredDiscList() {
      if (this.selectedGenre === "all") {
        return this.discList;
      }
      return this.discList.filter(
        (element) => element.genre === this.selectedGenre
      );
    },
  },
  methods: {
    getApiList() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          // handle success
          this.discList = result.data.response;
          console.log("Recupero la lista dall'API");
        })
        .catch((error) => {
          // handle error
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss" scoped>
/* Importo _variables.scss */
@import "../assets/scss/partials/_variables.scss";

main {
  height: calc(100vh - 76px);
  background-color: $bk-color;
  overflow-y: auto;
}
</style>
