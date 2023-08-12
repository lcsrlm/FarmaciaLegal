<template>

<div class="form-container">
    <h1>Formulário de Cadastro de medicamentos</h1>

    <form @submit.prevent="$emit('cadastrar', medicamento, laboratorio, preco)">
        <input type="text" placeholder="Informe o nome do medicamento" v-model="medicamento">
        <input type="text" placeholder="Informe o nome do laboratório" v-model="laboratorio">
        <input type="number" placeholder="Informe o preço" v-model="preco">
        <button>Cadastrar</button>
    </form>
</div>
</template>

<script>
export default {
    data() {
        return {
            medicamento: "",
            laboratorio: "",
            preco: "",
        }
    }
    }

</script>

<style scoped>

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

.form-container form {
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