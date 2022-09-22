<script>
  import axios from "axios";
  export default {
    data() {
      return {
        cep: "",
        endereco: {},
      };
    },
    methods: {
      async buscar() {
        const url = `https://viacep.com.br/ws/${this.cep}/json/`;
        const res = await axios.get(url);
        this.endereco = res.data;
      },
    },
  };
  </script>
<template>
  <h1>Consultar Cep:</h1>
  <form @submit.prevent="buscar">
    <input type="text" v-model="cep" placeholder="Digite o CEP" />
    <button type="submit">Consultar</button>
  </form>
  <form>
    <label for="rua">Logradouro: </label>
    <input type="text" v-model="endereco.logradouro" />

    <label for="num">Numero: </label>
    <input type="text" v-model="endereco.numero" />

    <label for="bairro">Bairro: </label>
    <input type="text" v-model="endereco.bairro" />

    <label for="localidade">Cidade: </label>
    <input type="text" v-model="endereco.localidade" />

    <label for="uf">UF: </label>
    <input type="text" v-model="endereco.uf" />

    <label for="ibge">IBGE: </label>
    <input type="text" v-model="endereco.ibge" />

    <label for="gia">Gia: </label>
    <input type="text" v-model="endereco.gia" />

    <label for="ddd">DDD: </label>
    <input type="text" v-model="endereco.ddd" />

    <label for="siafi">Siafi: </label>
    <input type="text" v-model="endereco.siafi" />
  </form>
  {{ endereco }}
</template>
<style></style>
