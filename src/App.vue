<script setup>
import { reactive } from "vue";

// import { createApp } from 'vue';

const estado = reactive({
  num1: "",
  num2: "",
  soma: "0",
});

function soma(event) {
  estado.soma = parseInt(estado.num1) + parseInt(estado.num2);  
  console.log(estado.soma)
}
</script>

<template>
  <hr />

  <h1>Resutlado: {{ estado.soma }}</h1>
  <label>Calculadora EBAC</label>
  <br />
  <input type="number" @change=" estado.num1 = e.target.value" />
  <br />
  <input type="number" @change=" estado.num2 = e.target.value" />
  <br />
  <button @click="soma">Somar</button>
  <br />
  <br />
  <!-- <div>Selected: {{ selected }}</div>

  <select v-model="selected">
    <option disabled value="">Please select one</option>
    <option>Somar</option>
    <option>Subtrair</option>
    <option>Multiplicar</option>
    <option>Dividir</option>
  </select> -->
</template>

<style scoped></style>
