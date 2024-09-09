<template>
  <div id="app">
    <h1>Cadastrar</h1>
    <p id="nomeErro" v-if="deuErro">O nome de usuario está invalido!</p>
    <input type="text" placeholder="Nome" v-model="nomeField">
    <input type="text" placeholder="e-mail" v-model="emailField">
    <input type="number" placeholder="idade" v-model="idadeField">
    <button @click="cadastroUser">Cadastrar</button>

    <h1>Guia Clientes</h1>
    <div v-for="cliente in orderClientes" :key="cliente.id">
      <Cliente :cliente="cliente" @meDelete="deletarUs($event)"/>

    </div>

  </div>
</template>

<script>
import _ from 'lodash';
import Cliente from './components/ClienteTeste.vue';
//import Produto from './components/ProdutoTeste.vue'

export default {
  name: 'app',
  data() {
    return {
      deuErro: false,
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
          if(this.nomeField == "" || this.nomeField.length < 3 || this.nomeField == undefined || this.nomeField == " "){
            this.deuErro = true;
          } else {
          this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.idadeField, id: Date.now()})
          this.nomeField = "";
          this.emailField = "";
          this.idadeField = "";
          this.deuErro = false;
          }
          
        },
        deletarUs: function($event) {
          var id = $event.idCliente;
          var novoArray = this.clientes.filter(cliente => cliente.id !== id);
          this.clientes = novoArray;
        }
      },
      computed: {
        orderClientes: function() {
          return _.orderBy(this.clientes, ['nome'], ['asc'])
        }
      }
}

</script>

<style scoped>
  #nomeErro {
    color: brown;
  }
</style>
