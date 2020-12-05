<template>
  <div class="container-fluid my-4 container-API" id="news">
    <h2 style="color: white;text-align:center;">Peliculas</h2>
    <hr width="100%" />
    <div class="row mt-md-5 mt-sm-5 mt-xs-5 container-movies">
      <div
        class="col-lg-6 col-xs-12 container-movie"
        v-for="movie in moviesFull"
        :key="movie.id"
      >
        <div class="d-flex justify-content-center align-items-center">
          <div class="p-3">
            <img :src="movie.Poster" :alt="movie.Title" width="230px" />
          </div>
          <div class="p-2">
            <h4 style="text-align: center">{{ movie.Title }}</h4>
            <div class="card">
              <h6 class="card-header">Director: {{ movie.Director }}</h6>
              <h6 class="card-header">Year: {{ movie.Year }}</h6>
              <h6 class="card-header">Genre: {{ movie.Genre }}</h6>
              <h6 class="card-header">Released: {{ movie.Released }}</h6>
              <h6 class="card-header">Rating imdb: {{ movie.imdbRating }}</h6>
              <div class="progress">
                <div
                  class="progress-bar progress-bar-striped progress-bar-animated"
                  role="progressbar"
                  :aria-valuenow="movie.imdbRating"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  :style="{ width: porcentaje(movie.imdbRating) }"
                ></div>
              </div>
            </div>
          </div>
          <div></div>
        </div>
        <div class="p-1 mx-2">
          <p>
            {{ movie.Plot }}
          </p>
        </div>
        <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
          <a class="btn btn-dark btn-lg" :href="movie.Pageimdb" target="_blank" role="button"
            >Leer más</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "APICard",
  props: ["member"],
  data() {
    return {
      moviesFull: [],
    };
  },
  methods: {
    porcentaje(n) {
      return String(n) + "%";
    },
  },
  mounted() {
    const apiKey = "39dddcd1";
    const search = "sea";
    let movies = [];
    axios
      .get(`http://www.omdbapi.com/?s=${search}&type=movie&apikey=${apiKey}`)
      .then((response) => (movies = response.data.Search.splice(1, 4)))
      .then((result) => {
        movies.forEach((movie) => {
          console.log("ded");
          axios
            .get(
              `http://www.omdbapi.com/?i=${movie.imdbID}&t=${movie.Title}&type=movie&y=${movie.Year}&plot=short&apikey=${apiKey}`
            )
            .then((response) => {
              let moviedata = response.data;
              console.log(moviedata);
              moviedata.Pageimdb = `https://www.imdb.com/title/${response.data.imdbID}/`;
              moviedata.imdbRating = String(
                parseFloat(moviedata.imdbRating) * 10
              );
              this.moviesFull.push(moviedata);
            })
            .catch((error) => {
              console.log(error);
            });
        });
      });
  },
};
</script>

<style scoped></style>
