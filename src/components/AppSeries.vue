<template>
  <div class="container-film">
    <img :src="`https://image.tmdb.org/t/p/w200/${series.backdrop_path}`" />
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
