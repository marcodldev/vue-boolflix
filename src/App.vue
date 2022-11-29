<template>
  <div id="app">
    <HeaderComp />
    <input @keyup.enter="cercafilm" v-model="film" type="text" />
    <MainComp :card="dataFilm"/>
  </div>
</template>

<script>
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    HeaderComp,
    MainComp,
  },
  data() {
    return {
      dataFilm: [],
      film: "",
    };
  },
  mounted() {},
  methods: {
    cercafilm() {
      axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=4574f1010abd642412416a37ebde8b6d&query=" +
            this.film
        )
        .then((response) => {
          console.log(response.data.results);
          //selezionare la varibaile di riferimento inizialmente vuota
          //abbinare i dati recuperati dall'axios
          this.dataFilm = response.data.results
        });
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}
</style>
