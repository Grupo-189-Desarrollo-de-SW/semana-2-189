<template>
  <header class="header">
    <section class="barra-menu" >
      <nav class="navbar navbar-expand-lg sticky-top navbar-dark bg-dark text-secondary-color-dark" >
        <a class="navbar-brand" href="# ">
          <img
            src="https://document-export.canva.com/-PNlM/DAEOzm-PNlM/71/thumbnail/NAto-58PNH5aV_hXNy5kJQ-0001-13723702838.png"
            width="30"
            height="30"
            class="d-inline-block align-top"
            alt=" "
            loading="lazy "
          />
             Bit Travel
        </a>
        <div class="collapse navbar-collapse justify-content-end" id="">
          <ul class="navbar-nav">
            <li class=" nav-item active ">
              <a class="nav-link" href="# "
                >Inicio<span class="sr-only">(current)</span>
              </a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#services ">Servicios</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#news ">Noticias</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#team ">Miembros</a>
            </li>
          </ul>
        </div>
      </nav>
    </section>

    <!-- carousel -->
    <div
      id="carouselExampleCaptions"
      class="carousel slide"
      data-ride="carousel"
    >
      <ol class="carousel-indicators">
        <li
          data-target="#carouselExampleCaptions"
          data-slide-to="0"
          class="active"
        ></li>
        <li
          data-target="#carouselExampleCaptions"
          data-slide-to="1"
          class=""
        ></li>
        <li
          data-target="#carouselExampleCaptions"
          data-slide-to="2"
          class=""
        ></li>
        <li
          data-target="#carouselExampleCaptions"
          data-slide-to="3"
          class=""
        ></li>
      </ol>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img
            src="https://vistapointe.net/images/rio-de-janeiro-2.jpg"
            alt=""
            width="1240px"
            height="500px"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>Rio de Janeiro - Brazil</h5>
            <p>Celebra la cultura brasileña en el lugar donde nació la samba y disfruta de las asombrosas maravillas naturales que la ciudad tiene para ofrecer.</p>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="https://procolombia.co/noticias/sites/default/files/sanandres_grande.jpg"
            alt=""
            width="1240px"
            height="500px"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>San Andrés - Colombia</h5>
            <p>Ven a la isla San Andrés, un auténtico paraíso con cerca de cuarenta sitios para bucear, las mejores playas del Caribe y un mar de siete colores.</p>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="https://www.costacruceros.es/content/dam/costa/inventory-assets/ports/DXB/dubai.jpg"
            alt=""
            width="1240px"
            height="500px"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>Dubái</h5>
            <p>
              Descubre la sorprendente metrópolis árabe cuyo lema es "si puedes soñarlo, nosotros podemos construirlo".
            </p>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="https://www.carlosandcharlies.com/wp-content/uploads/2019/07/Sin-t%C3%ADtulo-1.jpg"
            alt=""
            width="1240px"
            height="500px"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5 style="color: azure">Cancún - México</h5>
            <p>
              Cancún es considerado el destino de playa más visitado de México y quizás del mundo. Tiene con qué, playas de arena fina, lugares arqueológicos, paisajes que deslumbran, comida que deleita al paladar y artesanías que todo turista quiere comprar.
            </p>
          </div>
        </div>
      </div>
      <a
        class="carousel-control-prev"
        href="#carouselExampleCaptions"
        role="button"
        data-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Siguiente</span>
      </a>
      <a
        class="carousel-control-next"
        href="#carouselExampleCaptions"
        role="button"
        data-slide="next"
      >
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Anterior</span>
      </a>
    </div>
  </header>
</template>

<script>
export default {
  name: "PageHeader",
};
</script>

<style scoped>
    
</style>
