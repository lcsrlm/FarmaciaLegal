<template>
  <div class="card">
    <p v-if="favorito"></p>
    <img :width="120" src="https://dmvfarma.vtexassets.com/arquivos/ids/196865/caixa-medicamento-2021.png?v=637695586068000000" alt="Imagem do medicamento" />
    <p>Nome: {{ nome }}</p>
    <p>Laboratório: {{ laboratorio }}</p>
    <p>Preço: {{ preco }}</p>
    <p>Favorito: {{ favorito ? 'Sim' : 'Não' }}</p>
    <button @click="$emit('favoritar', id)">Favoritar</button>
   
  </div>
</template>
<script>
export default {
  props: ['nome', 'laboratorio', 'preco', 'favorito', 'id']
}
</script>
<style scoped>
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: calc(100%/4 - 2em);
  margin: 1em;
  background-color: transparent;
  gap: 8px;
}
  
</style>
