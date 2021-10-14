<template>
    <div class="container">
        <div class="table-responsive">
            <table class="table table-hover">
                <thead>
                    <th>Titulo</th>
                    <th>Encargado</th>
                    <th>Prioridad</th>
                    <th>Fecha Vencimiento</th>
                    <th>Notas</th>
                </thead>
                <tbody>
                    <tr v-for="Dato, index in FilasTabla" :key="index">
                        <td>{{Dato.title}}</td>
                        <td>{{Dato.manager}}</td>
                        <td>{{Dato.priority}}</td>
                        <td>{{Dato.final_date}}</td>
                        <td>{{Dato.note}}</td>
                    </tr>
                </tbody>
            </table>

        </div>
        
    </div>
    
</template>

<script>
export default {
    name: 'Tabla',
    props: {
        FilasTabla : Array
    }
}
</script>