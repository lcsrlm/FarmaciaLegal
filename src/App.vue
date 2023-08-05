<template>
  <div>
    <Header>

    </Header>
    <FormularioNovoMedicamento @cadastrar="AdicionarMedicamento">

    </FormularioNovoMedicamento>
    <CardMedicamento 
      v-if="!!listaMedicamentos"
      v-for="medicamento in listaMedicamentos"
      :key="medicamento.id"
      @favoritar="FavoritarMedicamento" 
      :nome="medicamento.nome" 
      :laboratorio="medicamento.laboratorio" 
      :preco="medicamento.preco" 
      :id="medicamento.id" 
    />
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import FormularioNovoMedicamento from "./components/FormularioNovoMedicamento.vue"
import CardMedicamento from "./components/CardMedicamento.vue"

export default {
  components: {
    Header,
    FormularioNovoMedicamento,
    CardMedicamento
  },
  data() {
    return {
      listaMedicamentos: []
    }
  },

  methods: {
    AdicionarMedicamento(nome, laboratorio, preco) {
      event.preventDefault()
      if(nome === "" || laboratorio === "" || preco === 0){
        alert("Preencha todos os dados")
        return
      }
      const novoMedicamento= {
        nome: nome,
        laboratorio: laboratorio,
        preco: preco,
        favorito: false,
        id: this.listaMedicamentos.length +1
      }
      this.listaMedicamentos.push(novoMedicamento)
    }
  }
}
</script>

<style>
</style>
