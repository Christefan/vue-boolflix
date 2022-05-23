<template>
  <main>
    <div class="container py-4">
      <div class="row row-cols-5">
        <!-- <div class="container-film">
          <h3>Titolo</h3>
          <h4>Titolo Originale</h4>
          <p>lingua</p>
          <p>voto</p>
        </div>
        <div class="container-film">
          <h3>Titolo</h3>
          <h4>Titolo Originale</h4>
          <p>lingua</p>
          <p>voto</p>
        </div>
        <div class="container-film">
          <h3>Titolo</h3>
          <h4>Titolo Originale</h4>
          <p>lingua</p>
          <p>voto</p>
        </div>
        <div class="container-film">
          <h3>Titolo</h3>
          <h4>Titolo Originale</h4>
          <p>lingua</p>
          <p>voto</p>
        </div>
        <div class="container-film">
          <h3>Titolo</h3>
          <h4>Titolo Originale</h4>
          <p>lingua</p>
          <p>voto</p> -->
        <AppFilm
          v-for="(items, index) in filmSelect"
          :key="index"
          :film="items"
        />
        <AppSeries
          v-for="(items, index) in seriesSelect"
          :key="index"
          :series="items"
        />
      </div>
    </div>
  </main>
</template>

<script>
import AppFilm from "./AppFilm.vue";
import AppSeries from "./AppSeries.vue";
export default {
  name: "AppMain",
  components: {
    AppFilm,
    AppSeries,
  },
  props: {
    filmSelect: Array,
    seriesSelect: Array,
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: aqua;
  min-height: 90vh;
}
.container-film {
  padding: 1rem;
  margin: 0.1rem;
  text-align: center;
  height: 400px;
  background-color: #2e3a46;
  color: white;
}
</style>
