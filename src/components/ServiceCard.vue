<template>
    <div class="card h-100 text-center">
      <div class="d-flex justify-content-center p-2">
        <img class="w-100" :src="service.image" alt="service.title">
      </div>
      <div class="card-body">
        <h4 class="card-title font-weight-bold">{{service.title}}</h4>
        <p class="card-text">
          {{service.descripcion}}
        </p>
        <a href="#" class="btn btn-dark">Más detalles</a>
      </div>
    </div>
</template>

<script>
export default {
  name: "ServiceCard",
  props:{
      service:Object,
  }
};
</script>

<style scoped></style>
