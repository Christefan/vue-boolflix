<template>
  <div class="container-film">
    <div class="Mokup">
      <img
        v-if="film_Series.poster_path !== null"
        :src="`https://www.themoviedb.org/t/p/w342${film_Series.poster_path}`"
      />
      <img v-else src="../assets/img/Post-non-trovato.jpg" alt="" />
    </div>
    <img
      class="post"
      :src="`https://www.themoviedb.org/t/p/w200${film_Series.backdrop_path}`"
    />
    <div class="text">
      <h3>Titolo: {{ film_Series.title || film_Series.name }}</h3>
      <h4>
        Titolo-originale:
        {{ film_Series.original_title || film_Series.original_name }}
      </h4>
      <p>
        Lingua:
        <img
          v-if="flags.includes(film_Series.original_language)"
          :src="require(`../assets/img/${film_Series.original_language}.png`)"
        />
        <img v-else :src="require(`../assets/img/tutti.png`)" />
      </p>
      <p>
        voto:
        <i
          v-for="(item, index) in star"
          :key="index"
          v-bind:class="
            index < Math.ceil(film_Series.vote_average / 2)
              ? 'fas fa-star'
              : 'far fa-star'
          "
        ></i>
      </p>
      <p>overview: {{ film_Series.overview }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppFilmSeries",
  data() {
    return {
      star: 5,
      flags: ["en", "fr", "it"],
    };
  },
  props: {
    film_Series: Object,
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
    img {
      width: 15px;
      height: 15px;
    }
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
