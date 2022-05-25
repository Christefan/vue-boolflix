<template>
  <div class="container-film">
    <div class="Mokup">
      <img :src="`https://www.themoviedb.org/t/p/w342${film.poster_path}`" />
    </div>
    <img
      class="post"
      :src="`https://www.themoviedb.org/t/p/w200${film.backdrop_path}`"
    />
    <div class="text">
      <h3>Titolo: {{ film.title }}</h3>
      <h4>Titolo-originale: {{ film.original_title }}</h4>
      <p>Lingua: {{ film.original_language }}</p>
      <p>
        voto:
        <i
          v-for="(item, index) in 5"
          :key="index"
          v-bind:class="
            index < Math.ceil(film.vote_average / 2)
              ? 'fas fa-star'
              : 'far fa-star'
          "
        ></i>
      </p>
      <p>overview: {{ film.overview }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppFilm",
  data() {
    return {
      star: 0,
    };
  },
  props: {
    film: Object,
  },
};
</script>

<style lang="scss" scoped>
.container-film {
  position: relative;
  .Mokup {
    display: block;
  }
  img {
    width: 100%;
    height: 500px;
  }
  .post {
    display: none;
  }
  .text {
    display: none;
    p {
      font-size: 13px;
    }
  }
  &:hover .text {
    display: block;
  }
  &:hover .Mokup {
    display: none;
  }
}
</style>
