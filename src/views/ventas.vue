<template>
<div>
    <div class="ventas">
    <h1> ventas</h1>
    <lista :Juegos="Juegos" :totalJuegosstock="totalJuegosstock"></lista>
    </div>
</div>
</template>

<script>
import {mapState, mapGetters} from 'vuex';
import lista from '../components/lista'
export default {
    name: 'presentación',
    // props: {},
    data: function(){
        return {}
    },
    computed: {
        ...mapState(['Juegos']),
        ...mapGetters(['totalJuegos','JuegosParaVender', 'totalJuegosstock']),
    },
    methods: {
    
    },
     components: {
         'lista':lista
     },
}
</script>

<style scoped>
        .ventas{
        text-align:left;
        display:flex;
        flex-direction:column;
        width:400px;
        justify-content:center;
        margin:auto ;
        margin-top:50px;
    }
    h1{
        text-align:center
    }
</style>