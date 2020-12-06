<template>
  <div id="app">

    <!-- Header -->

    <!-- Fin del Header -->

    <!-- Seccion API -->

    <!-- Fin seccion API -->

    <!-- Sección de Equipo -->
         <div class="container-fluid container-miembros">
      <h2 style="color: white;text-align:center;">Equipo</h2>
      <hr width="100%" />
      <div class="row justify-content-center mb-5">
        <div class="col mt-5 ancho-minimo" v-for="item in members" :key="item.id">
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
  components: {TeamCard,
  },
  data(){
    return {
      members: [{
        codigo : 1 ,
        nombre : 'Gustavo García L.' ,
        descripcion : 'Ingeniero de sistemas, desarrollador Full Stack, Laravel, Node, Git, JS, JAVA.' ,
        rol : 'Desarrollador FullStack' ,
        image : require('../public/images/Gustavo.jpg')
      },
      {
        codigo : 2 ,
        nombre : 'Carlos Galindez' ,
        descripcion : 'Analista de interfaz de usuario, UI, UX, Bootstrap.' ,
        rol : 'Desarrollador Frontend' ,
        image : require('../public/images/Carlos.png')
      },
      {
        codigo : 3 ,
        nombre : 'Juan J Neira' ,
        descripcion : 'Data Analyst, css, js, html, php, py developer.' ,
        rol : 'Desarrollador backend' ,
        image : require('../public/images/juanneira.jpg')
      },
      {
        codigo : 4 ,
        nombre : 'David Hernández' ,
        descripcion : 'Business Consultant, success projector, finance advisor.' ,
        rol : 'Desarrollador de Negocios' ,
        image : require('../public/images/fotodave.jpg')
      },
      {
        codigo : 5 ,
        nombre : 'Carlos Gutierrez' ,
        descripcion : 'Wireframe planner, UX, UI designer.' ,
        rol : 'Desarrollador Frontend' ,
        image : require('../public/images/carlos-gutierrez.jpg')
      }]
      }
    }
}
</script>

