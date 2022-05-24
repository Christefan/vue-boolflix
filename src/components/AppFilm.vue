<template>
  <div class="container-film">
    <img :src="`https://image.tmdb.org/t/p/w200/${film.backdrop_path}`" />
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
  methods: {
    votoStelle() {
      //Controllo funzione
      //Proviamo a inviare i valori tramite funzione
      //P.s sono stato per 5 ore a capire come risolvere
      // this.star = this.film.vote_average;
      // console.log(this.star);
      // return Math.round(this.star / 2);
      // return this.star;
      // let prova;
      // for(i=0; i<5; i++){
      //   if(i < Math.round(this.film.vote_average / 2)){
      //     this.star=1;
      //   }
      //   this.star=0;
      // }
    },
  },
};
</script>

<style lang="scss" scoped></style>
