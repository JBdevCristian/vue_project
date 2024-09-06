<template>
  <div id="app">
    <input type="text" v-model="clienteRogerio.nome">
    <input type="text" v-model="clienteRogerio.email">
    <h1>Guia Clientes</h1>
    <Cliente :cliente="clienteRogerio" :showIdade="false"/>

  </div>
</template>

<script>
import Cliente from './components/ClienteTeste.vue'
//import Produto from './components/ProdutoTeste.vue'

export default {
  name: 'app',
  data() {
    return {
      clienteRogerio: {
        nome: "Rogerio",
        idade: 25,
        email: "paypalteste@gmail.com"
      }
    }
  },
  components: {
    Cliente,
    //Produto
  }
}

</script>

<style>

</style>
