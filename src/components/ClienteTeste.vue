<template>
    <div>
        <h1>Informações do Cliente</h1>
        <input type="text" v-model="nome">
        <hr>
        <input type="text" v-model="nacionalidade">
        <hr>    
        <p>Nome do cliente: {{ nome }}</p>
        <p>Idade do cliente: {{ idade }}</p>
        <p>Nacionalidade: {{ nacionalidade }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
        nome: "Cristian",
        idade: 22,
        nacionalidade: "brasileira"
        }
    }
}
</script>

<style scoped>


</style>