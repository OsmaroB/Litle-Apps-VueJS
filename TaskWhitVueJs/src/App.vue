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
        <Table/>
      </div>
  </div>
</template>

<script>
import Table from './components/Table'
import Insert from './components/Insert'
export default {
  name: 'App',
  components:{
    Table,
    Insert
  },
}
</script>

<style>
</style>
