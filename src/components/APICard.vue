<template>
  <div>
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
    </div>
    <div class="p-1 mx-2">
      <p>
        {{ movie.Plot }}
      </p>
    </div>
    <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
      <a
        class="btn btn-dark btn-lg"
        :href="movie.Pageimdb"
        target="_blank"
        role="button"
        >Leer más</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "APICard",
  props: ["movie"],
  methods: {
    porcentaje(n) {
      return String(n) + "%";
    },
  },
};
</script>

<style scoped>

</style>
