<template>

<div class="form-container">
    <h1>Formulário de Cadastro de medicamentos</h1>
    <form>
        <input type="text" placeholder="Informe o nome do medicamento" v-bind="nomeMedicamento">
        <input type="text" placeholder="Informe o nome do laboratório" v-bind="nomeLaboratorio">
        <input type="number" placeholder="Informe o preço" v-bind="preco">
        <button @click="$emit('cadastrar')">Cadastrar</button>
    </form>
</div>
</template>

<script>
export default {
    props: ['nomeMedicamento', 'nomeLaboratorio', 'preco']
}

</script>

<style>

input[type=number]::-webkit-inner-spin-button { 
    -webkit-appearance: none;   
}

input[type=number] { 
   -moz-appearance: textfield;
   appearance: textfield;
}

.form-container h1 {
    text-align: center;
    margin-top: 10px;
    margin-bottom: 10px;

    font-family: sans-serif;
    font-size: 16pt;
}

.form-container form{
    display: flex;
    flex-direction: row;
    justify-content: space-around;

}

.form-container input, button {
    height: 4vh;
    width: 20vw;

    border-radius: 4px;
    border: 1px solid grey;
}

.form-container ::placeholder {
    font-size: 10pt;
    text-align: center;
}

</style>