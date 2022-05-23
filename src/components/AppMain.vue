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
      </div>
    </div>
  </main>
</template>

<script>
import AppFilm from "./AppFilm.vue";
export default {
  name: "AppMain",
  components: {
    AppFilm,
  },
  props: {
    filmSelect: Array,
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: aqua;
  min-height: 90vh;
}
</style>
