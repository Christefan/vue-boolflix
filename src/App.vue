<template>
  <div id="app">
    <AppHeader @searchClick="search($event)" />
    <AppMain :filmSelect="films" :seriesSelect="series" />
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
      api_key: "9c3cf0691abc4035223bf72d4f521110",
    };
  },
  methods: {
    search(searchKey) {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: this.api_key,
            query: searchKey,
          },
        })
        .then((item) => {
          console.log(item);
          this.films = item.data.results;
          console.log("Film = " + this.films);
        });
      axios
        .get("https://api.themoviedb.org/3/search/tv", {
          params: {
            api_key: this.api_key,
            query: searchKey,
          },
        })
        .then((item) => {
          console.log(item);
          this.series = item.data.results;
          console.log("Serie tv = " + this.series);
        });
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "~@fortawesome/fontawesome-free/css/all.min.css";
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
