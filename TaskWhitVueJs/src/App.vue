<template>
  <div id="app">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <br>
            <h1 class="text-center">Aplicacion de tareas</h1> 
          </div>
        </div>
        <br>
        <!--Importante aca importamos las tablas-->
        <Table/>
      </div>
  </div>
</template>

<script>
import Table from './components/Table'
export default {
  name: 'App',
  components:{
    Table
  },
}
</script>

<style>
</style>
