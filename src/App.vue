<template>
  <div id="app">
    
    <!-- Header -->

    <!-- Fin del Header -->

    <!-- Seccion API -->

    <!-- Fin seccion API -->

    <!-- Sección de Equipo -->
    <div class="container-fluid">
    <div class="row justify-content-center mb-5">
      <div class="col mt-5" v-for="(item, index) of team" :key="index">
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
import TeamCard from './components/TeamCard.vue'

export default {
  name: 'App',
  components: {
    TeamCard
  },
  data(){
    return{
      team : [
        {
          codigo : 1,
          nombre: "Juan Jose Neira Cote",
          descripcion: 
            " Hace parte de Mision TIC 2022, y se encuentra en desarrollo del ciclo 3 - Desarrollo de sotfware",
          rol : "Empíric WE",
          imagen: "images/Juan.jpg",
        },
        {
          codigo : 2,
          nombre: "Gustavo Adolfo Garcia Londoño",
          descripcion: 
            " Hace parte de Mision TIC 2022, y se encuentra en desarrollo del ciclo 3 - Desarrollo de sotfware",
          rol : "Ingeniero de Sistemas",
          imagen: "images/Gustavo.jpg",
        },
        {
          codigo : 3,
          nombre: "David Esteban Hernández Garzón",
          descripcion: 
            " Hace parte de Mision TIC 2022, y se encuentra en desarrollo del ciclo 3 - Desarrollo de sotfware",
          rol : "Ingeniero de Sonido",
          imagen: "images/David.jpg",
        },
        {
          codigo : 4,
          nombre: "Carlos Alfredo Galindez Muñoz",
          descripcion: 
            " Hace parte de Mision TIC 2022, y se encuentra en desarrollo del ciclo 3 - Desarrollo de sotfware",
          rol : "Ingeniero de Procesos",
          imagen: "images/Carlos_Galindez.jpg",
        },
        {
          codigo : 5,
          nombre: "Carlos Gutiérrez",
          descripcion: 
            " Hace parte de Mision TIC 2022, y se encuentra en desarrollo del ciclo 3 - Desarrollo de sotfware",
          rol : "Ingeniero de Procesos",
          imagen: "images/Carlos_Gutierrez.jpg",
        },
      ]
    }
  }
}
</script>

