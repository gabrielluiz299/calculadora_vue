<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Seletor from './components/Seletor.vue'
import Formulario from './components/Formulario.vue'

  const numerosParaCalcular = reactive({
    operation: 'somar',
    num1: '0',
    num2: '0'
  })

  const getOperacoesSomar = (a, b) => {
    return a + b;
  }

  const getOperacoesSubtrair = (a, b) => {
    return a - b;
  }

  const getOperacoesDividir = (a, b) => {
    return a / b;
  }

  const getOperacoesMultiplicar = (a, b) => {
    return a * b;
  }

  const getOperacoes = () => {
    const { operacoes, num1, num2 } = numerosParaCalcular;

    switch (operacoes) {
      case 'somar':
        return getOperacoesSomar();
      case 'subtrair':
        return getOperacoesSubtrair();
      case 'dividir':
        return getOperacoesDividir();
      case 'multiplicar':
        return getOperacoesMultiplicar();
      default:
        return "erro";
    }
  }
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Seletor :operation="operation"/>
    <Formulario />
  </div>
</template>

<style scoped>
</style>
