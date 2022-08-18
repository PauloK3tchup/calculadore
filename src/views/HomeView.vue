<script>
export default {
  data() {
    return {
      preco: 0,
      porcentagem: 0,
      pessoas: 0,
      valor_final: 0,
      valor: 0,
    };
  },

  methods: {
    calcular() {
      const preco = this.preco;
      const porcentagem = this.porcentagem;
      const pessoas = this.pessoas;
      let valor_final = 0;
      valor_final = (preco * (1 + porcentagem / 100)) / pessoas;
      console.log(valor_final);
    },
  },
};
</script>
<template>
  <label for="preco">Valor do produto</label>
  <input v-model="preco" id="preco" type="number" /><br />
  <label for="jorgeta">Selecione a qualidade do serviço</label>
  <select v-model="porcentagem" id="jorgeta">
    <option value="" disabled>Selecione</option>
    <option value="5">Repugnante (5%)</option>
    <option value="10">Horrendo (10%)</option>
    <option value="15">Mais ou menos (15%)</option>
    <option value="20">Bah (20%)</option>
    <option value="25">Morbástico (25%)</option>
    <option value="30">Grutástico (30%)</option></select
  ><br />
  <label for="preco">Quantas pessoas vão pagar</label>
  <input v-model="pessoas" id="pessoas" type="number" /> <br />
  <button @click="calcular()">Calcular</button>
  <h1>{{ preco }} + {{ porcentagem }}% ÷ {{ pessoas }} = sexo</h1>
</template>
<style></style>
