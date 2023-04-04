<script setup>
import { reactive } from 'vue';

  const estado = reactive({
    number1:0,
    number2:0,
    operation:'soma',
  })

  const result = () => {
    const {number1, number2, operation} = estado;
    switch (operation) {
        case 'soma':
          return number1 + number2;
        case 'subtração':
          return number1 - number2;
        case 'multiplicação':
          return number1 * number2;
        case 'divisão':
          return number1 / number2;
        default:
          return 0;
    }
  }

</script>

<template>
  <div>
    <label for="number1">Número 1:</label>
    <input id="number1" type="number" v-model="estado.number1">

    <label for="number2">Número 2:</label>
    <input id="number2" type="number" v-model="estado.number2">

    <label for="operation">Operação:</label>
    <select id="operation" v-model="estado.operation">
      <option value="soma">Adição</option>
      <option value="subtração">Subtração</option>
      <option value="multiplicação">Multiplicação</option>
      <option value="divisão">Divisão</option>
    </select>

    <p>Resultado: {{ result() }}</p>
  </div>
</template>


<style scoped></style>
