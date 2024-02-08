<script setup>
import { reactive } from 'vue';

  const numerosParaCalcular = reactive({
    operacoes: 'somar',
    numeros: '',
  })

  const cadastrarNumero = () => {
    const numeroNovo = {
      numero: numerosParaCalcular.numeros,
    }
    numerosParaCalcular.numeros.push(numeroNovo);
      }

  const getOperacoesSomar = () => {
    return a + b;
  }

  const getOperacoesSubtrair = () => {
    return a - b;
  }

  const getOperacoesDividir = () => {
    return a / b;
  }

  const getOperacoesMultiplicar = () => {
    return a * b;
  }

  const getOperacoes = () => {
    const { operacoes } = numerosParaCalcular;

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
     <div class="row">
      <header class="p-5 mb-4 bg-light rounded-3">
      <h1>Calculadora Aritmética</h1>
    </header>
    <div>
      <div class="col">
        <label for="operation">Operações:</label>
        <select @change="evento => numerosParaCalcular.operacoes = evento.target.value" class="form-control">
        <option value="somar">Somar</option>
        <option value="subtrair">Subtrair</option>
        <option value="dividir">Dividir</option>
        <option value="multiplicar">Multiplicar</option>
      </select>
      {{ numerosParaCalcular.operacoes }}
    </div>
       <form @submit.prevent="guardarNumero">
         <div class="row">
          <div class="col">
            <label for="num1">Número 1:</label>
            <input @change="evento => numerosParaCalcular.numeros = evento.target.value" required id="num1" v-model="num1" type="number">
          </div>
          <div class="col">
            <label for="num2">Número 2:</label>
            <input @change="evento => numerosParaCalcular.numeros = evento.target.value" required id="num2" v-model="num2" type="number">
          </div>
          <div class="col"><p> Resultado: {{ getOperacoes }}</p></div>
        </div>
       </form>
       {{ numero1 }}
     </div>
    </div>
  </div>
</template>

<style scoped>
</style>
