<template>
  <div>
    <Header>

    </Header>
    <FormularioNovoMedicamento @cadastrar="AdicionarMedicamento">

    </FormularioNovoMedicamento>
    <div class="card-container">
      <CardMedicamento v-if="!!listaMedicamentos" v-for="medicamento in listaMedicamentos" :key="medicamento.id"
      @favoritar="FavoritarMedicamento" @remover="RemoverMedicamento" :nome="medicamento.nome" :laboratorio="medicamento.laboratorio"
      :preco="medicamento.preco" :id="medicamento.id" :favorito="medicamento.favorito"/>
    </div>

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

      if (nome === "" || laboratorio === "" || preco === 0) {
        alert("Preencha todos os dados")
        return
      }
      const novoMedicamento = {
        nome: nome,
        laboratorio: laboratorio,
        preco: preco,
        favorito: false,
        id: this.listaMedicamentos.length + 1
      }
      this.listaMedicamentos.push(novoMedicamento)
    },
    FavoritarMedicamento(id) {
      this.listaMedicamentos = this.listaMedicamentos.map(item => {
        if (item.id == id) {
          item.favorito = !item.favorito
        }
        return item
      })
    },
    RemoverMedicamento(id) {
    this.listaMedicamentos = this.listaMedicamentos.filter(medicamento => medicamento.id !== id)
  }
  }
}


</script>

<style>
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}


</style>
