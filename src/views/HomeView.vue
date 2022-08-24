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
      document.getElementById("final").innerHTML = "R$" + valor_final;
    },
  },
};
</script>
<template>
  <div class="tudo">
    <div class="inputes">
      <label for="preco">Valor do produto</label>
      <input class="inputiu" v-model="preco" id="preco" type="number" /><br />
      <label for="jorgeta">Selecione a qualidade do serviço</label>
      <select class="inputiu" v-model="porcentagem" id="jorgeta">
        <option value="0" disabled>Selecione</option>
        <option value="5">Repugnante (5%)</option>
        <option value="10">Horrendo (10%)</option>
        <option value="15">Mais ou menos (15%)</option>
        <option value="20">Bah (20%)</option>
        <option value="25">Morbástico (25%)</option>
        <option value="30">Grutástico (30%)</option></select
      ><br />
      <label for="preco">Quantas pessoas vão pagar</label>
      <input class="inputiu" v-model="pessoas" id="pessoas" type="number" />
      <br />
      <!-- <button @click="calcular()">Calcular</button> -->
      <div class="choice act" @click="calcular()">
        <i class="fa fa-angle-double-right"></i>
        <span>CALCULAR</span>
      </div>
    </div>
    <div class="resultado">
      <h3>O valor que você pagará é:</h3>
      <h1 id="final"></h1>
    </div>
  </div>
  <div class="sans">
    <img
      src="https://c.tenor.com/PRdbAP7eu60AAAAC/sans-undertale.gif"
      alt="sand"
      class="sa"
      title="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
    />
  </div>
</template>
<style>
@import url(//db.onlinewebfonts.com/c/7cc6719bd5f0310be3150ba33418e72e?family=Comic+Sans+MS);
@import url("https://fonts.googleapis.com/css2?family=VT323&display=swap");

body {
  font-family: "Comic Sans MS";
  background-color: black;
}

.tudo {
  color: white;
  margin: 50px;
  border: 3px solid white;
  padding: 20px;
  width: 50%;
  display: inline-block;
}

.inputiu {
  margin-left: 15px;
  padding: 4px;
  font-family: "Comic Sans MS";
  border-radius: 8px;
  background-color: black;
  color: #ff9900;
  border: 2px solid #ff9900;
}

.inputiu:hover {
  color: #ffff33;
  border: 2px solid #ffff33;
}

.sans {
  width: 40%;
  float: right;
}

.choices {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  max-width: 80rem;
  margin: 0 auto;
  padding: 1rem 0 0 0;
}

.choice {
  width: 7.5rem;
  text-align: center;
  font-size: 2rem;
  border: 2px solid #ff9900;
  padding: 0.5rem 1rem;
  transition: all 0.2s ease;
  color: #ff9900;
  margin-top: 10px;

  display: flex;
  align-items: center;
  justify-content: flex-start;
  font-family: "VT323", monospace;
}

.choice:hover {
  color: #ffff33;
  border: 2px solid #ffff33;
  cursor: grab;
  transform: scale(1.2);
}

i {
  padding-right: 0.5rem;
}

.fa-heart {
  color: crimson;
}
</style>
