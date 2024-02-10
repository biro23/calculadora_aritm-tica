<template>
  <div class="app">
    <h1>Calculadora Aritmética</h1>
    <input type="number" v-model.number="data.numero1" @input="calcular" />
    <select v-model="data.operacao" @change="calcular">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <br />
    <input type="number" v-model.number="data.numero2" @input="calcular" />
    <div>Resultado: {{ data.resultado }}</div>
  </div>
</template>

<script setup>
const data = {
  numero1: 0,
  numero2: 0,
  operacao: '+',
  resultado: 0
}

const calcular = () => {
  switch(data.operacao) {
    case '+':
      data.resultado = Number(data.numero1) + Number(data.numero2);
      break;
    case '-':
      data.resultado = data.numero1 - data.numero2;
      break;
    case '*':
      data.resultado = data.numero1 * data.numero2;
      break;
    case '/':
      data.resultado = data.numero1 / data.numero2;
      break;
  }
}
</script>

<style scoped>
.app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  margin-top: 50px;
}
input,
select {
  margin: 10px;
  padding: 5px;
  background-color: aqua;
}
</style>
