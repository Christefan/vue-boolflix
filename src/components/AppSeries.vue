<template>
  <div class="container-film">
    <h3>{{ series.name }}</h3>
    <h4>{{ series.original_name }}</h4>
    <p>{{ series.original_language }}</p>
    <p>{{ series.vote_average }}</p>
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
