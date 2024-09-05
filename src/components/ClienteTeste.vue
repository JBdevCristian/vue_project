<template>
    <div class="cadastro">
        <h1>Informações do Cliente</h1>
        <h4>Nome do cliente: {{ cliente.nome }}</h4>
        <p>E-mail: {{ cliente.email }}</p>
        <p>Descição: {{ descicao }}</p>
        <p v-if="showIdade">Idade do cliente: {{ cliente.idade }}</p>
        <p v-else>O cliente decidiu esconder a idade!!</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
       }
    },
    props: { //sempre passar o objeto props
        cliente: Object, //definir tipo
        showIdade: Boolean,
        descicao: String

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

</style>