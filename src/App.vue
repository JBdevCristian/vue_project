<template>
  <div id="app">
    <input type="text" v-model="cliente.nome">
    <input type="text" v-model="cliente.email">
    <h1>Guia Clientes</h1>
    <Cliente nome="rodolfo" email="teste@gmail.com" idade="50"/>
    <Cliente :nome="cliente.nome" :email="cliente.email" :idade="cliente.idade"/>
    <Cliente/>
    <Cliente/>

  </div>
</template>

<script>
import Cliente from './components/ClienteTeste.vue'
//import Produto from './components/ProdutoTeste.vue'

export default {
  name: 'app',
  data() {
    return {
      cliente: {
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
