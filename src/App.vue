<template>
  <div id="app">
    <!-- Header -->

    <page-header> </page-header>

    <!-- Fin del Header -->

    <!-- Seccion API -->

    <!-- Fin seccion API -->
    <div class="container-fluid my-4 container-API" id="news">
      <h2 style="color: white;text-align:center;">Peliculas</h2>
      <hr width="100%" style="color: white" />
      <div class="row mt-md-5 mt-sm-5 mt-xs-5">
        <div
          class="col-lg-6 col-xs-12 container-movie"
          v-for="item in moviesFull"
          :key="item.id"
        >
          <APICard :movie="item"></APICard>
        </div>
      </div>
    </div>
    <!-- Sección de Equipo -->
    <div class="container-fluid container-miembros" id="team">
      <h2 style="color: black;text-align:center;">Equipo</h2>
      <hr width="100%" />
      <div class="row justify-content-center mb-5">
        <div
          class="col mt-5 ancho-minimo"
          v-for="item in members"
          :key="item.id"
        >
          <team-card :member="item"></team-card>
        </div>
      </div>
    </div>
    <!-- Fin sección Equipo -->

    <!-- Sección Footer -->

    <!-- Fin sección Footer -->
  </div>
</template>

<script>
import axios from "axios";
import APICard from "./components/APICard.vue";
import PageHeader from "./components/PageHeader.vue";
import TeamCard from "./components/TeamCard.vue";

export default {
  name: "App",
  components: {
    APICard,
    PageHeader,
    TeamCard,
  },
  data() {
    return {
      moviesFull: [],
      members: [
        {
          codigo: 1,
          nombre: "Gustavo García L.",
          descripcion:
            "Ingeniero de sistemas, desarrollador Full Stack, Laravel, Node, Git, JS, JAVA.",
          rol: "Desarrollador FullStack",
          image: require("../public/images/Gustavo.jpg"),
        },
        {
          codigo: 2,
          nombre: "Carlos Galindez",
          descripcion: "Analista de interfaz de usuario, UI, UX, Bootstrap.",
          rol: "Desarrollador Frontend",
          image: require("../public/images/Carlos.png"),
        },
        {
          codigo: 3,
          nombre: "Juan J Neira",
          descripcion: "Data Analyst, css, js, html, php, py developer.",
          rol: "Desarrollador backend",
          image: require("../public/images/juanneira.jpg"),
        },
        {
          codigo: 4,
          nombre: "David Hernández",
          descripcion:
            "Business Consultant, success projector, finance advisor.",
          rol: "Desarrollador de Negocios",
          image: require("../public/images/fotodave.jpg"),
        },
        {
          codigo: 5,
          nombre: "Carlos Gutierrez",
          descripcion: "Wireframe planner, UX, UI designer.",
          rol: "Desarrollador Frontend",
          image: require("../public/images/carlos-gutierrez.jpg"),
        },
      ],
    };
  },
  methods: {
    extraerPeliculas() {
      const apiKey = "39dddcd1";
      const search = "sea";
      axios
        .get(`http://www.omdbapi.com/?s=${search}&type=movie&apikey=${apiKey}`)
        .then((response) => response.data.Search.splice(1, 4))
        .then((movies) => {
          movies.forEach((movie) => {
            axios
              .get(
                `http://www.omdbapi.com/?i=${movie.imdbID}&t=${movie.Title}&type=movie&y=${movie.Year}&plot=short&apikey=${apiKey}`
              )
              .then((response) => {
                let moviedata = response.data;
                moviedata.Pageimdb = `https://www.imdb.com/title/${moviedata.imdbID}/`;
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
  },
  created() {
    this.extraerPeliculas();
  },
};
</script>

<style scoped>
.container-API {
  background-color: #27057d;
  box-shadow: 4px 4px 4px 4px rgba(39, 5, 125, 0.2);
}
hr {
  height: 1px;
  border-bottom-width: 1px;
  border-bottom-style: solid;
  padding-top: 0px;
  margin-top: 0px;
  margin-bottom: 0px;
}
.container-movie {
  background-color: #ededed;
  border: 10px solid #27057d;
  border-radius: 20px;
}
</style>
