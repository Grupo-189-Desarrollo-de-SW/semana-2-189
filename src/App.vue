<template>
  <div id="app">
    <!-- Header -->

    <!-- Fin del Header -->

    <!-- Seccion API -->

    <!-- Fin seccion API -->

    <!-- Sección de Equipo -->

    <!-- Fin sección Equipo -->

    <!-- Sección Footer -->

    <footer-card :members="members"></footer-card>
    <!-- Fin sección Footer -->
  </div>
</template>

<script>
import FooterCard from "./components/FooterCard";

export default {
  name: "App",
  components: {
    FooterCard,
  },
  data() {
    return {
      members: [
        {
          nombres: "Gustavo Adolfo",
          apellidos:"García Londoño",
          rol: "Desarrollador FullStack",
          email:"gustavogarcia@utp.edu.co"
        },
        {
          nombres: "Carlos Alfredo",
          apellidos:"Galindez Muñoz",
          rol: "Desarrollador Frontend",
          email:"alfredgalindez@gmail.com"
        },
        {
          nombres: "Juan José",
          apellidos:"Neira Cote",
          rol: "Desarrollador backend",
          email:"juanjneira@gmail.com"
        },
        {
          nombres: "David Esteban",
          apellidos:"Hernández Garzón",
          rol: "Desarrollador de Negocios",
          email:"daves1998@hotmail.com"
        },
        {
          nombres: "Carlos Andrés",
          apellidos:"Gutiérrez Cruz",
          rol: "Desarrollador Frontend",
          email:"contacto10@gmail.com"
        }
      ],
    };
  },
};
</script>
