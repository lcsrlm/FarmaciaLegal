  <template>
  <div class="card">
    <p v-if="favorito"></p>
    <img :width="120" src="https://dmvfarma.vtexassets.com/arquivos/ids/196865/caixa-medicamento-2021.png?v=637695586068000000" alt="Imagem do medicamento" />
    <p>Nome: {{ nome }}</p>
    <p>Laboratório: {{ laboratorio }}</p>
    <p>Preço: {{ preco }}</p>
    <button class="fav-button" @click="$emit('favoritar', id)">{{ favorito ? 'Remover dos favoritos' : 'Adicionar aos favoritos' }}</button>
    <button class="remove-button" @click="removerMedicamento">Remover</button>
   
  </div>
</template>
<script>
export default {
  props: ['nome', 'laboratorio', 'preco', 'favorito', 'id'],
  methods: {
    removerMedicamento() {
      this.$emit('remover', this.id)
    }
  }
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

  font-family: sans-serif;
}
.remove-button {
  background: none;
  border: none;
  padding: 0;
  color: #ff0000; 
  cursor: pointer;
  font-size: small;
  text-decoration: underline;
}

.fav-button {
  width: 10vw;
}

</style>
