<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col-6 text-white">
          Questo è il genere che sarà visualizzato {{ visualize }}
        </div>
        <div class="col-6">
          <button
            class="btn btn-primary"
            @click="getFilteredDiscList(visualize)"
          >
            click
          </button>
        </div>
      </div>
      <div class="row row-cols-1 row-cols-md-3 row-cols-lg-5 g-4 py-5">
        <!-- Ciclo sulla pagina che consente di generare una singola card -->
        <SingleDisc
          v-for="(element, index) in discList"
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
    //this.getFilteredDiscList(this.visualize);
  },
  updated() {
    this.getFilteredDiscList(this.visualize);
  },
  data() {
    return {
      discList: [],
      filteredDiscList: [],
    };
  },
  props: ["visualize"],
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
    getFilteredDiscList(genre) {
      console.log("Genero l'array filtrato per genere");
      this.filteredDiscList = [];
      if (genre == "all") {
        this.filteredDiscList = [...this.discList];
      } else {
        this.discList.forEach((element) => {
          if (element.genre.toLowerCase() == genre) {
            this.filteredDiscList.push(element);
          }
        });
      }
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
