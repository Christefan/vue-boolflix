<template>
  <div class="container-film">
    <div class="Mokup">
      <img :src="`https://image.tmdb.org/t/p/w342/${series.poster_path}`" />
    </div>
    <img
      class="post"
      :src="`https://image.tmdb.org/t/p/w200/${series.backdrop_path}`"
    />
    <div class="text">
      <h3>{{ series.name }}</h3>
      <h4>{{ series.original_name }}</h4>
      <p>{{ series.original_language }}</p>
      <p>
        voto:
        <i
          v-for="(item, index) in 5"
          :key="index"
          v-bind:class="
            index < Math.ceil(series.vote_average / 2)
              ? 'fas fa-star'
              : 'far fa-star'
          "
        ></i>
      </p>
      <p>overview: {{ series.overview }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppSeries",
  props: {
    series: Object,
  },
};
</script>

<style scoped lang="scss">
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
