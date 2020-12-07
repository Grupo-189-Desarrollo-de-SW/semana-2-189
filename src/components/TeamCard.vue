<template>
    <div class="card bg-dark">
        <!--div class="card text-white "-->
            <div class="justify-content-center p-2 text-white">
            <img width="100%" height="auto" :src="member.image"/>
            <div class="card-body">
                <h5 class="card-title text-center">{{member.codigo}}</h5>
                <h5 class="card-title">{{member.nombre}}</h5>
                <h6 class="card-title">{{member.rol}}</h6>
                <p class="card-text">{{member.descripcion}}</p>
                <div class="card-footer">
                </div>
            </div>
            </div>
        <!--/div-->
    </div>
</template>

<script>
    export default {
        name: "TeamCard",
        props: ['member']
    }
</script>

<style>
.ancho-minimo {
    min-width:240px;
    max-width: 320px !important;
}
</style>
