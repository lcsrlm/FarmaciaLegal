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
      listaMedicamentos: [{
        nomeMedicamento: "",
        nomeLaboratorio: "",
        preco: ""
      }]
    }
  },
  components: {
    Header,
    FormularioNovoMedicamento
  },
  methods: {
    cadastrar() {
      alert('usuario cadastrou')

    }
  }
}
</script>

<style></style>
