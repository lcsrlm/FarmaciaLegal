<template>
  <div>
    <Header>

    </Header>
    <FormularioNovoMedicamento @cadastrar="cadastrar">

    </FormularioNovoMedicamento>
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import FormularioNovoMedicamento from "./components/FormularioNovoMedicamento.vue"

export default {
  data() {
    return {
      listaMedicamentos: []
    }
  },
  components: {
    Header,
    FormularioNovoMedicamento
  },
  methods: {
    cadastrar(novoMedicamento) {
      this.listaMedicamentos.push(novoMedicamento)
      alert('Medicamento cadastrado com sucesso')

    }
  }
}
</script>

<style></style>
