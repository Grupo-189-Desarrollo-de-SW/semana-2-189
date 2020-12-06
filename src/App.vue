<template>
  <div id="app">
    <!-- Header -->

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

    <!-- Sección de Equipo -->

    <!-- Fin sección Equipo -->

    <!-- Sección Footer -->

    <!-- Fin sección Footer -->
  </div>
</template>

<script>
import ServiceCard from "./components/ServiceCard.vue";

export default {
  name: "App",
  components: {
    ServiceCard,
  },
  data() {
    return {
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
};
</script>

<style scoped>
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

.container-service {
  background-color: #ededed;
  border: 10px solid #27057d;
  border-radius: 20px;
}


</style>
