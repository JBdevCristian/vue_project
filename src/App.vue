<template>
  <div id="app">
    <input type="text" v-model="clienteRogerio.nome">
    <input type="text" v-model="clienteRogerio.email">
    <h1>Guia Clientes</h1>
    

    <div v-for="cliente in clientes" :key="cliente.id">
      <Cliente :cliente="cliente" :showIdade="true"/>
      <h4>Edit: </h4>
      <input type="text" v-model="cliente.nome">
      <input type="text" v-model="cliente.email">
    </div>

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
      },
      clientes: [
        {
        id: 1,
        nome: "Rogerio",
        idade: 25,
        email: "paypalteste@gmail.com"
        },
        {
        id: 2,
        nome: "Mario",
        idade: 18,
        email: "paypalteste@gmail.com"
        },
        {
        id: 3,
        nome: "Giovanna",
        idade: 24,
        email: "paypalteste@gmail.com"
        },
        {
        id: 4,
        nome: "Regina Cazé",
        idade: 50,
        email: "paypalteste@gmail.com"
        }
      ]
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
