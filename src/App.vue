<template>
  <div id="app">
    <!-- Header -->

    <page-header> </page-header>

    <!-- Fin del Header -->

    <!-- Seccion de servicios -->
    <div class="container-fluid my-4 container-services" id="services">
      <h2 style="color: white;text-align:center;">Servicios</h2>
      <hr width="100%" style="color: white" />
      <div class="row justify-content-center mb-5">
        <div
          class="col-sm-6 col-xs-12 col-lg-4 mt-5 py-2 container-service"
          v-for="item in services"
          :key="item.id"
        >
          <service-card :service="item"></service-card>
        </div>
      </div>
    </div>
    <!-- Fin servicios -->

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

    <footer-card :members="members"></footer-card>
    <!-- Fin sección Footer -->
  </div>
</template>

<script>
import axios from "axios";
import APICard from "./components/APICard.vue";
import PageHeader from "./components/PageHeader.vue";
import TeamCard from "./components/TeamCard.vue";
import ServiceCard from "./components/ServiceCard.vue";
import FooterCard from "./components/FooterCard";

export default {
  name: "App",
  components: {
    APICard,
    PageHeader,
    TeamCard,
    ServiceCard,
    FooterCard,
  },
  data() {
    return {
      moviesFull: [],
      members: [
        {
          codigo: 1,
          nombre: "Gustavo García L.",
          nombres: "Gustavo Adolfo",
          apellidos: "García Londoño",
          email: "gustavogarcia@utp.edu.co",
          descripcion:
            "Ingeniero de sistemas, desarrollador Full Stack, Laravel, Node, Git, JS, JAVA.",
          rol: "Desarrollador FullStack",
          image: require("../public/images/Gustavo.jpg"),
        },
        {
          codigo: 2,
          nombre: "Carlos Galindez",
          nombres: "Carlos Alfredo",
          apellidos: "Galindez Muñoz",
          email: "alfredgalindez@gmail.com",
          descripcion: "Analista de interfaz de usuario, UI, UX, Bootstrap.",
          rol: "Desarrollador Frontend",
          image: require("../public/images/Carlos.png"),
        },
        {
          codigo: 3,
          nombre: "Juan J Neira",
          nombres: "Juan José",
          apellidos: "Neira Cote",
          email: "juanjneira@gmail.com",
          descripcion: "Data Analyst, css, js, html, php, py developer.",
          rol: "Desarrollador backend",
          image: require("../public/images/juanneira.jpg"),
        },
        {
          codigo: 4,
          nombre: "David Hernández",
          descripcion:
            "Business Consultant, success projector, finance advisor.",
          nombres: "David Esteban",
          apellidos: "Hernández Garzón",
          email: "daves1998@hotmail.com",
          rol: "Desarrollador de Negocios",
          image: require("../public/images/fotodave.jpg"),
        },
        {
          codigo: 5,
          nombre: "Carlos Gutierrez",
          nombres: "Carlos Andrés",
          apellidos: "Gutiérrez Cruz",
          email: "contacto10@gmail.com",
          descripcion: "Wireframe planner, UX, UI designer.",
          rol: "Desarrollador Frontend",
          image: require("../public/images/carlos-gutierrez.jpg"),
        },
      ],

      services: [
        {
          title: "Reserve su hotel",
          descripcion:
            "Podemos ubicar alojamientos para todos los gustos, desde hotelesbaratos, céntricos, complejos de lujo, hasta resorts todo incluido, ideales para unas vacaciones inolvidables o descansar con comodidad en nuestros viajes de negocios. Hay más de 800 000 hoteles alrededor del mundo, para elegir el que se acomode a nuestra necesidad, ahorrando tiempo, dinero.",
          image: require("../public/images/servicio1.jpg"),
        },
        {
          title: "Vuelos nacionales e internacionales",
          descripcion:
            "Elija la ciudad o el país al que quiere viajar y las fechas de ida y regreso. Al escoger su fecha de ida, visualizará los precios promedio hasta un mes después de la fecha elegida. Puede identificar los precios más baratos del mes por el color verde. Haga click en la fecha de regreso que más le convenga, y conozca la oferta de diferentes aerolíneas con varias posibilidades de rutas, horarios y escalas.",
          image: require("../public/images/servicio2.jpg"),
        },
        {
          title: "Los mejores paquetes turisticos",
          descripcion:
            "Al comprar tus paquetes turísticos puedes conseguir un valor más bajo en tu viaje, ya que al sumar un alojamiento o un carro, obtienes un descuento significativo. ¡Comprar paquetes de viaje siempre te va a resultar más barato! Puedes armar tus paquetes a medida, ahorrar en el valor total y gastar ese dinero en tu viaje. ¡Aprovecha planes turísticos a un sinfín de destinos!",
          image: require("../public/images/servicio3.jpg"),
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
.container-services {
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

.container-service .container-movie {
  background-color: #ededed;
  border: 10px solid #27057d;
  border-radius: 20px;
}
</style>
