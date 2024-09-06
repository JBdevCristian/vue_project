<template>
  <div id="app">
    <h1>Cadastrar</h1>
    <input type="text" placeholder="Nome" v-model="nomeField">
    <input type="text" placeholder="e-mail" v-model="emailField">
    <input type="number" placeholder="idade" v-model="idadeField">
    <button @click="cadastroUser">Cadastrar</button>

    <h1>Guia Clientes</h1>
    <div v-for="cliente in clientes" :key="cliente.id">
      <Cliente :cliente="cliente" :showIdade="true"/>
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
      nomeField: "",
      emailField: "",
      idadeField: 0,
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
        }
      ]
    }
  },
  components: {
    Cliente,
    //Produto
  },
  methods: {
        cadastroUser: function() {
          this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.idadeField, id: Date.now()})
          this.nomeField = "";
          this.emailField = "";
          this.idadeField = "";
        }
      }
}

</script>

<style>

</style>
