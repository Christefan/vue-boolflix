<template>
  <main>
    <div class="container py-4">
      <h2>Film</h2>
      <div class="row row-cols-5">
        <AppFilm
          v-for="(items, index) in filmSelect"
          :key="index"
          :film="items"
        />
      </div>
      <h2>Serie</h2>
      <div class="row row-cols-5">
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
