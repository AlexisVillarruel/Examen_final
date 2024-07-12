<template>
  <template>
    <h5>Listado de Peliculas</h5>
    <div class="movie-list">
      <div class="movie-grid">
        <div class="movie-item" v-for="movie in movies" :key="movie.id">
          <ItemMovie :movie="movie" />
        </div>
      </div>
    </div>
  </template>
</template>

<script>
import ItemMovie from "./ItemMovie.vue";

// const fetch = require("node-fetch");

// const url =
//   "https://api.themoviedb.org/3/discover/movie?include_adult=false&include_video=false&language=en-US&page=1&sort_by=popularity.desc";
// const options = {
//   method: "GET",
//   headers: {
//     accept: "application/json",
//     Authorization:
//       "Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJjODRmMmUwODYxM2JmN2FlYTM1OGI0OTgzNDNkMWUwNiIsInN1YiI6IjVmZTUxM2M3ZTE4Yjk3MDAzYzg5NzE3MCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.StJwmra-PsBwZTOXWg3Y06VEu8CGfAo8dXV7ZQ3RnIs",
//   },
// };

// fetch(url, options)
//   .then((res) => res.json())
//   .then((json) => console.log(json))
//   .catch((err) => console.error("error:" + err));

export default {
  name: "ListMovie",
  components: { ItemMovie },
  data() {
    return {
      movies: [],
    };
  },
  mounted() {
    this.loadmovies();
  },
  methods: {
    loadmovies() {
      var URL =
        "https://api.themoviedb.org/3/discover/movie?include_adult=false&include_video=false&language=en-US&page=1&sort_by=popularity.desc";
      this.$api
        .get(URL, {
          headers: {
            accept: "application/json",
            Authorization:
              "Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJjODRmMmUwODYxM2JmN2FlYTM1OGI0OTgzNDNkMWUwNiIsInN1YiI6IjVmZTUxM2M3ZTE4Yjk3MDAzYzg5NzE3MCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.StJwmra-PsBwZTOXWg3Y06VEu8CGfAo8dXV7ZQ3RnIs",
          },
        })
        .then((response) => {
          this.movies = response.data;
          console.log(JSON.stringify(response));
        })
        .catch((error) => {
          console.log("Ocurrio un error: " + error);
          this.$router.push("/");
        });
    },
  },
};
</script>

<style>
.product-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20xp;
}
</style>
