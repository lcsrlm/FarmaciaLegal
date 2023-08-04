<template>

<div class="form-container">
    <h1>Formulário de Cadastro de medicamentos</h1>
    <form>
        <input type="text" placeholder="Informe o nome do medicamento" v-model="nomeMedicamento">
        <input type="text" placeholder="Informe o nome do laboratório" v-model="nomeLaboratorio">
        <input type="number" placeholder="Informe o preço" v-model="preco">
        <button @submit="$emit('cadastrar')">Cadastrar</button>
    </form>
</div>
</template>

<script>
export default {
    data() {
        return {
            nomeMedicamento: "",
            nomeLaboratorio: "",
            preco: ""
        }
    },
    methods: {
        cadastrarMedicamento(){
            const novoMedicamento = {
                nomeMedicamento: this.nomeMedicamento,
                nomeLaboratorio: this.nomeLaboratorio,
                preco: this.preco
            }
            this.$emit('cadastrar', novoMedicamento)
            this.nomeMedicamento = ""
            this.nomeLaboratorio = ""
            this.preco = ""
        }
    }
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