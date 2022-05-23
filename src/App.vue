<template>
  <div id="app">
    <AppHeader @searchClick="saveFilm($event)" />
    <AppMain :filmSelect="filteredFilms" />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import axios from "axios";
export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      films: [],
      selectfilm: "",
    };
  },
  created() {
    axios
      .get(
        "https://api.themoviedb.org/3/search/movie?api_key=9c3cf0691abc4035223bf72d4f521110&query=la vita"
      )
      .then((item) => {
        console.log(item);
        this.films = item.data.results;
        console.log(this.films);
      });
  },
  computed: {
    filteredFilms() {
      let filerFilms = [];
      if (this.selectfilm != "") {
        filerFilms = this.films.filter((item) => {
          return item.title.toLowerCase().includes(this.selectfilm);
        });
      }
      return filerFilms;
    },
  },
  methods: {
    saveFilm: function (searchFilm) {
      this.selectfilm = searchFilm.toLowerCase();
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
