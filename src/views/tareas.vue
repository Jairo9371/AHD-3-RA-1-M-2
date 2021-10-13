<template>
    <div class="container mt-5">
        <div class="row">
            <div class="col-md-12">
                <h3 class="text-center">TAREAS</h3>
            </div>
            <div class="row">
                <div class="col-md-6">
                    <label for="">Titulo</label>
                    <input v-model="Titulo" type="text" class="form-control">

                </div>
                <div class="col-md-6">
                    <label for="check" class="form-check-label">Encargados</label>
                    <select v-model="Encargado" class="form-select" >
                    <option value="" selected disabled>Elige una Opción</option>
                    <option v-for="Dato, index in Encargados" :key="index" :value="Dato.Nombre">
                        {{Dato.Nombre}} {{Dato.Apellido}}
                    </option>
                </select>

                </div>

            </div>
            <div class="col-md-4">
                    <label for="check" class="form-check-label">Depósito</label>
                    <select v-model="Deposito" class="form-select" >
                    <option value="" selected disabled>Elige una Opción</option>
                    <option v-for="Dato, index in Depositos" :key="index" :value="Dato.id">
                        {{Dato.Descripcion}}
                    </option>
                </select>
            </div>
            <div class="col-md-4">
                    <label for="check" class="form-check-label">Progreso</label>
                    <select v-model="Progreso" class="form-select" >
                    <option value="" selected disabled>Elige una Opción</option>
                    <option v-for="Dato, index in Progresos" :key="index" :value="Dato.id">
                        {{Dato.Descripcion}}
                    </option>
                </select>
            </div>
            <div class="col-md-4">
                    <label for="check" class="form-check-label">Prioridad</label>
                    <select v-model="Prioridad" class="form-select" >
                    <option value="" selected disabled>Elige una Opción</option>
                    <option v-for="Dato, index in Prioridades" :key="index" :value="Dato.Descripcion">
                        {{Dato.Descripcion}}
                    </option>
                </select>
            </div>
        </div>
        <div class="row mt-3">
            <div class="col-md-4">
                <label for="">Fecha Inicio</label>
                <input class="form-control" v-model="FechaInicio" type="date" name="" id="">
            </div>
            <div class="col-md-4">
                <label for="">Fecha Vencimiento</label><br>
                <input class="form-control" v-model="FechaVencimiento" type="date" name="" id="">
            </div>
        </div>
        <div class="row mt-3">
            <div class="col-md-2">
                <label for="">Notas</label>
                <input v-model="Nota" class="form-control" type="number" name="" id="">
            </div>
        <div class="row f-grid mt-4 justify-content-end">
                <div class="col-md-2">
                <button @click="Guardar" class="btn btn-primary ">Guardar</button>
            </div>
        </div>
                <label for="">Lista de Comprobacion</label>
           
            
        </div>

        <hr>
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
    name : 'Tareas',
    data(){
        return{
            Encargados : [{
                id : 1,
                Nombre : "Jairo",
                Apellido : "Gregorio"
            },
            {
                id : 1,
                Nombre : "Lily",
                Apellido : "Hernandez"
            }
            ],

            Depositos : [ 
                {id : 1, Descripcion: 'Pendiente'},
                {id : 2, Descripcion: 'Validación'},
                {id : 3, Descripcion: 'Iniciado'},
                {id : 4, Descripcion: 'Producción'},
                {id : 5, Descripcion: 'Finalizado'}
            ],
            Progresos : [ 
                {id : 1, Descripcion: 'No Iniciada'},
                {id : 2, Descripcion: 'En curso'},
                {id : 3, Descripcion: 'Completada'}
            ],
            Prioridades : [ 
                {id : 1, Descripcion: 'Baja'},
                {id : 2, Descripcion: 'Mediana'},
                {id : 3, Descripcion: 'Alta'},
                {id : 4, Descripcion: 'Urgente'}
            ],
            Titulo : "",
            Encargado : "",
            Deposito : "",
            Progreso : "",
            Prioridad : "",
            FechaInicio : "",
            FechaVencimiento : "",
            Nota : "",
            ListaComprobacion : [],
            FilasTabla : []
        }
    },
    methods: {
        Guardar(){
            this.FilasTabla.push(
                {
                title: this.Titulo,
                manager: this.Encargado,
                priority: this.Prioridad,
                final_date: this.FechaVencimiento,
                note: this.Nota
            }
            );

        }
    }
}
</script>

