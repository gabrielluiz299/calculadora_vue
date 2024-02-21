<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Seletor from './components/Seletor.vue'
import Resultado from './components/Resultado.vue'

  const numerosParaCalcular = reactive({
    operacoes: 'somar',
    num1: '',
    num2: ''
  })

  const getOperacoes = () => {
    const {operacoes} = numerosParaCalcular;

    switch (operacoes) {
      case 'somar':
        return parseFloat(numerosParaCalcular.num1) + parseFloat(numerosParaCalcular.num2);
      case 'subtrair':
        return parseFloat(numerosParaCalcular.num1) - parseFloat(numerosParaCalcular.num2);
      case 'dividir':
        return parseFloat(numerosParaCalcular.num1) / parseFloat(numerosParaCalcular.num2);
      case 'multiplicar':
        return parseFloat(numerosParaCalcular.num1) * parseFloat(numerosParaCalcular.num2);
      default:
        return "erro";
    }
  }
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Seletor 
      :operacoes="evento=> numerosParaCalcular.operacoes = evento.target.value" 
      :num1="evento => numerosParaCalcular.num1 = evento.target.value" 
      :num2="evento => numerosParaCalcular.num2 = evento.target.value">
    </Seletor>
    <Resultado :num1="numerosParaCalcular.num1" :num2="numerosParaCalcular.num2" :result="getOperacoes()"/>
  </div>
</template>

<style scoped>
</style>
