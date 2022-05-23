<template>
  <div id="app">
    <AppHeader @searchClick="saveResearch($event)" />
    <AppMain :filmSelect="filteredFilms" :seriesSelect="filteredSeries" />
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
      series: [],
      // arrFilm_Series: [],
      searchAll: "",
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
        console.log("Film = " + this.films);
      });
    axios
      .get(
        "https://api.themoviedb.org/3/search/tv?api_key=9c3cf0691abc4035223bf72d4f521110&query=la vita"
      )
      .then((item) => {
        console.log(item);
        this.series = item.data.results;
        console.log("Serie tv = " + this.series);
      });
  },
  computed: {
    filteredFilms() {
      let filerFilms = [];
      if (this.searchAll != "") {
        filerFilms = this.films.filter((item) => {
          return item.title.toLowerCase().includes(this.searchAll);
        });
      }
      return filerFilms;
    },
    filteredSeries() {
      let filterSeries = [];
      if (this.searchAll != "") {
        filterSeries = this.series.filter((item) => {
          return item.name.toLowerCase().includes(this.searchAll);
        });
      }
      return filterSeries;
    },
  },
  methods: {
    saveResearch: function (searchKey) {
      this.searchAll = searchKey.toLowerCase();
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
