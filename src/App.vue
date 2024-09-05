<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <Cliente/>
    <Produto/>
    <Cliente/>
    <Produto/>
    <Cliente/>
    <Produto/>
    <Cliente/>
    <Produto/>
    <Cliente/>
    <Produto/>
    <Cliente/>
    <Produto/>

  </div>
</template>

<script>
import Cliente from './components/ClienteTeste.vue'
//import Produto from './components/ProdutoTeste.vue'

export default {
  name: 'app',
  components: {
    Cliente,
    //Produto
  }
}

</script>

<style>

</style>
