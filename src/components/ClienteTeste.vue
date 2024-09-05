<template>
    <div class="cadastro">
        <h1>Informações do Cliente</h1>
        <h4>Nome do cliente: {{ nome }}</h4>
        <p>Descrição: {{ descricao }}</p>
        <p>E-mail: {{ email }}</p>
        <p>Idade do cliente: {{ idade }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
        descricao: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like)."
        }
    },
    props: { //sempre passar o objeto props
        nome: String, //definir tipo
        email: String, //definir tipo
        idade: Number, //definir tipo
        cliente: Object //definir tipo

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