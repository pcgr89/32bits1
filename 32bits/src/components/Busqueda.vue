<template>
    <div class="container">
        <p>Busqueda de Juegos</p>
        <input type="text" v-model="busqueda" />

        <p class="pt-4">Número de juegos disponibles:
        <span v-text="juegosDisponibles"></span>
        </p>

        <p>Cantidad de juegos totales:
        <span v-text="juegosTotales"></span>
        </p>

        <ListadoJuegos
        :entrada="busqueda"
        :busquedas="busquedaJuegos"
        :cantidadJuegos="cantidadDeJuegosTotalesStock">
        </ListadoJuegos>
 
    </div>
</template>

<script>
import {mapGetters} from "vuex";
import ListadoJuegos from './ListadoJuegos.vue'

export default {
    name: "Busqueda",
    data() {
        return {
            // v-model busqueda apunta aqui
            busqueda: '', 
            totalJuegos: ''
        }
    },
    components: {
        ListadoJuegos
    },
    computed: {
        ...mapGetters([
            'cantidadDeJuegosTotalesStock',
            'juegosDisponibles'
        ]),
        juegosTotales() {
            let total = 0;
            for (const iterator of this.$store.getters.cantidadDeJuegosTotalesStock) {
                total = total + parseInt(iterator.stock);
            }
            return total;
        },
        busquedaJuegos(){
            return this.$store.getters.busquedaJuegos(this.busqueda);
        }
    }
};
</script>
