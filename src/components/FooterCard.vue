<template>
  <footer class="page-footer text-white pt-4" style="margin-top: 30px;">
    <!-- Footer Text -->
    <div class="container-fluid text-center">
      <!-- Grid row -->
      <div class="row">
        <!-- Grid column -->
        <div
          class="col-md-6 mt-md-0 mt-3 text-center"
          style="margin-bottom: 30px;"
        >
          <!-- Content -->
          <img src="../../public/images/logo_footer.png" width="250" />
          <p>
            Este sitio web fue realizado por el equipo 189 en el marco del ciclo
            III (Desarrollo de Software) del programa misión TICS 2022 con la
            colaboración de las personas aquí mencionadas.
          </p>
          <div class="d-flex justify-content-around flex-wrap">
            <img
              alt="Logo Mision TIC 2022"
              src="../../public/images/misiontic_logo.png"
              width="80px"
            />
            <img
              alt="Logo MinTIC"
              src="https://www.mintic.gov.co/portal/604/channels-507_logo_nuevo.png"
              height="60px"
            />
          </div>
          <br />
          <br />
          <a
            style="color: white; text-align: center;"
            href="https://github.com/Grupo-189-Desarrollo-de-SW/semana-2-189"
            target="_blank"
            >Repositorio Github</a
          >
        </div>
        <!-- Grid column -->
        <!-- Grid column -->
        <div class="col-md-6 mb-md-0 mb-3 d-flex flex-wrap justify-content-around align-items-center">
          <!-- Content -->
          <div class="text-center px-2" v-for="item in members" :key="item.id">
            <p>
              <strong>{{item.nombres}}<br />{{item.apellidos}}</strong
              ><br />{{item.rol}}<br /><span class="texto_peque"
                >{{item.email}}</span
              >
            </p>
          </div>
        </div>
        <!-- Grid column -->
      </div>
      <!-- Grid row -->
    </div>
    <!-- Footer Text -->

    <!-- Copyright -->
    <div class="footer-copyright text-center py-1">
      © BitTravel | 2020
    </div>
    <!-- Copyright -->
  </footer>
</template>

<script>
export default {
  name: "FooterCard",
  props: {
    members: Array,
  },
};
</script>

<style scoped>
footer {
  background-color: #5e17eb;
  color: white;
  overflow: hidden;
  border-radius: 0 0 25px 25px;
  padding: 25px;
}

a {
  cursor: pointer;
  text-decoration: underline;
}

.texto_peque {
    font-size: 50%;
}
</style>
