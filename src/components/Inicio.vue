<template>
    <div>
        <!-- Titulo y subtitulo vienen del store > state. Se llaman a través de computed property ...mapState -->
        <h1 v-text="titulo"></h1>
        <h2 v-text="subtitulo"></h2>
    </div>
</template>

<script>
import {mapState} from 'vuex'

export default {
    name: 'Inicio',
    data() {
        return {
            
        }
    },
    computed: {
        ...mapState(['titulo', 'subtitulo'])
    }
}
</script>

<style scoped>
h1,h2 {
    text-align: center;
}
</style>