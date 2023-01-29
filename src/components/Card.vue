<template>
    <div class="col-12 col-sm-4 col-md-3 col-lg-2 mb-3 mb-3">
        <div class="card" style="width: 10rem;">
            <img :src=producto.image class="card-img-top" :alt="`imagen-${producto.title}`" style="height: 9.5rem;padding: 15px;">
            <div class="card-body">
                <h6 class="card-title">{{ producto.title }}</h6>
                <p class="card-text"><span>$ {{ producto.price }}</span></p>
                <a href="#" class="btn btn-secondary" @click="agregar(producto)">Comprar</a>
            </div>
        </div>
    </div>
</template>

<script>
import { useStore } from 'vuex'
export default {
    props : ['producto'],
    setup(){
        const store = useStore();
        const agregar = (producto)=> {
            console.log(producto);
            store.dispatch('agregarAlCarro', producto);
        }

        return {agregar};
    }
}
</script>

<style lang="scss" scoped>

</style>