<template>
    <div :class="{'cadastro': !premium, 'cadastro-premium': premium}">
        <h1>Informações do Cliente</h1>
        <h4>Nome do cliente: {{ cliente.nome }}</h4>
        <p>E-mail: {{ cliente.email | processarEmail}}</p>
        <p v-show="showIdade">Idade do cliente: {{ cliente.idade }}</p>
        <p>ID do cliente: {{ cliente.id }}</p>
        <button @click="mudarCor">Mudar Cor</button>
        <button @click="deletarUsuario">Deletar</button>
        
    </div>
</template>

<script>
export default {
    data() {
        return {
            premium: false
       }
    },
    props: { //sempre passar o objeto props
        cliente: Object, //definir tipo

    },
    methods: {
        mudarCor: function() {
            console.log("Testando")
            this.premium = !this.premium;
        },
        deletarUsuario: function() {
            console.log("vindo do filho")
            this.$emit("meDelete", {idCliente: this.cliente.id, componente: this})
        }
    },
    filters: {
        processarEmail: function(value) {
            return value.toUpperCase();
        }
    }
}
</script>

<style scoped>
    .cadastro {
        font-family: "Rubik", system-ui;
        padding: 2%;
        background: black;
        color: white;
        margin-bottom: 10px;
    }

    .cadastro-premium {
        font-family: "Rubik", system-ui;
        padding: 2%;
        background: rgb(72, 204, 39);
        color: rgb(0, 0, 0);
        margin-bottom: 10px;
    }

</style>