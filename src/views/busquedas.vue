<template>
<div>
    <div class="filtro">
        <filtro :Juegos="JuegosConFiltro" :totalJuegos="totalJuegos" @buscar="search"></filtro>
    </div>

</div>
</template>

<script>
import {mapState, mapGetters} from 'vuex';
import filter from '../components/filtro';
export default {
    name: 'presentacion',
    data: function(){
        return {
            search_codigo:''
        }
    },
    computed: {
          ...mapState(['Juegos']),
          ...mapGetters(['totalJuegos','JuegosParaVender']),
            JuegosConFiltro(){
      return this.JuegosParaVender.filter((juego)=> juego.codigo.includes(this.search_codigo))
    }
    },
    methods: {

    search(e){

        this.search_codigo = e.search_codigo;  
    
    }
    },
    components: {
        'filtro':filter,
    },
}
</script>
<style scoped>
    .filtro{
        display:flex;
        justify-content:center;
        margin-top:40px;
        font-size:20px;
    }

</style>