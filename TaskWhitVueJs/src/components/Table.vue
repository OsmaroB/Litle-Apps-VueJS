<template>
    <div>
        <div class="row">
            <div class="col-12">
                <div class="container">
                    <form v-on:submit.prevent="addTask">
                        <div class="form-row">
                            <div class="col-10">
                            <input type="text" autofocus v-model="newTask.tarea" class="form-control" placeholder="Agregar tarea">
                            </div>
                            <div class="col">
                                <button class="btn btn-success" type="submit">Add</button>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </div>
        <br>
        <div class="row">
            <div class="col-12">
                <table class="table">
                <thead class="thead-dark">
                    <tr>
                        <th>#</th>
                        <th>Estado</th>
                        <th>Descripcion</th>
                        <th>Eliminar</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(tarea, index) in task" v-bind:key="tarea.tarea">
                        <th scope="row">{{index+1}}</th>
                        <th>
                            <div v-if="tarea.estado">
                                <input type="checkbox" v-on:click="changeState(tarea,tarea.estado)">
                                <label class="form-check-label" >
                                    En ejecucion
                                </label>
                            </div>
                            <div v-else>
                                <input type="checkbox"  checked  v-on:click="changeState(tarea,tarea.estado)">
                                <label  class="form-check-label" for="estado">
                                    Terminado
                                </label>
                            </div>
                        </th>
                        <th>
                            {{tarea.tarea}}
                        </th>
                        <th>
                            <button class="btn btn-danger" v-on:click="deleteTask(tarea)">Eliminar</button>
                        </th>
                    </tr>
                </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<style media="screen">

</style>

<script>
export default {
    data(){
        return{
            task:[
                {
                    tarea:'Estudiar',
                    estado: true,
                },
                {
                    tarea: 'Programar',
                    estado: false
                }
            ],
            newTask:{}
        }
    },
    methods:{
        addTask(){
            this.newTask.estado = true;
            this.task.push(this.newTask);
            this.newTask = {};
        },
        changeState(tarea,estadoActual){
            if(estadoActual){
                this.task[this.task.indexOf(tarea)].estado = false;
            }else{
                this.task[this.task.indexOf(tarea)].estado = true;
            }
            
        },
        deleteTask(tarea){
            this.task.splice(this.task.indexOf(tarea),1)
        }
    }
}
</script>