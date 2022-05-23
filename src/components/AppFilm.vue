<template>
  <div class="container-film">
    <h3>{{ film.title }}</h3>
    <h4>{{ film.original_title }}</h4>
    <p>{{ film.original_language }}</p>
    <p>{{ film.vote_average }}</p>
  </div>
</template>

<script>
export default {
  name: "AppFilm",
  props: {
    film: Object,
  },
};
</script>

<style lang="scss" scoped>
.container-film {
  padding: 1rem;
  margin: 0.1rem;
  text-align: center;
  height: 400px;
  background-color: #2e3a46;
  color: white;
}
</style>
