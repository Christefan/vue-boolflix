<template>
  <main>
    <div class="container py-4">
      <h2 v-if="filmSelect != ''">Film</h2>
      <div class="row row-cols-5">
        <AppFilmSeries
          v-for="(items, index) in filmSelect"
          :key="index"
          :film_Series="items"
        />
      </div>
      <h2 v-if="seriesSelect != ''">Serie</h2>
      <div class="row row-cols-5">
        <AppFilmSeries
          v-for="(items, index) in seriesSelect"
          :key="index"
          :film_Series="items"
        />
      </div>
    </div>
  </main>
</template>

<script>
import AppFilmSeries from "./AppFilmSeries.vue";
export default {
  name: "AppMain",
  components: {
    AppFilmSeries,
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
  height: 530px;
  background-color: #2e3a46;
  color: white;
}
</style>
