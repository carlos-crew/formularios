<template lang="">
     <h3 class="my-4"> Total de proyectos: {{numeroProyectos}}</h3>
   <div class="table-responsive">
         <table class="table table-dark  table-hover">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Proyecto</th>
                    <th>Tipo</th>
                    <th>Urgente</th>
                    <th>Completado</th>
                    <th>Borrado</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(proyect, index) in proyectos">
                    <td>{{index+1}}</td>
                    <td>{{proyect.proyecto}}</td>
                    <td>{{proyect.tipo}}</td>
                    <td @click="cambiarUrgencia(proyect, 'urgente')"
                        :class="proyect.urgente ? 'bg-success':'bg-danger'">{{proyect.urgente ? "Si":"No"}}</td>
                    <td @click="cambiarUrgencia(proyect, 'completado')"
                        :class="proyect.completado ?  'bg-success':'bg-danger' "> {{proyect.completado ?
                        "Completado" : "Incompleto" }}</td>
                    <td>
                        <button  class="btn btn-danger my-4" @click="limpiarUno(proyect, index)">Eliminar</button>
                    </td>
                </tr>
            </tbody>
            </table>
</div>


    <div class="col-6 text-end" >
        <button class="btn btn-danger my-4" @click="limpiarData()">Limpiar Datos</button>
       
    </div>
   
</template>


<script>
    export default{
        props:[
            'numeroProyectos', 'proyectos', 'cambiarUrgencia', 'limpiarData', 'limpiarUno'

        ],
    }
</script>
