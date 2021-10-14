<template>
    <div class="container mt-5">
       <formulario @filas="DatosTabla" ></formulario>

       <hr>

       <tabla :FilasTabla="DatosTablaHijo"></tabla>
    </div>
</template>

<script>

import formulario from '../components/formulario.vue'
import tabla from '../components/tabla.vue'

export default {
    name : 'Tareas',
    components : {
        formulario,
        tabla
    },
    data(){
        return {
            DatosTablaHijo:[]
        }
    },
    methods:{
        DatosTabla(Valores){
            this.DatosTablaHijo = Valores;
        }
    }
}
</script>

