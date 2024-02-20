<script setup>
    const props = defineProps(['numerosParaCalcular', 'numerosParaCalcular.num1', 'numerosParaCalcular.num2'])
</script>

<template>
    <form @submit.prevent="props.numerosParaCalcular">
         <div class="row">
          <div class="col">
            <label for="num1">Número 1:</label>
            <input v-model="props.numerosParaCalcular.num1" required id="num1" type="number">
          </div>
          <div class="col">
            <label for="num2">Número 2:</label>
            <input v-model="props.numerosParaCalcular.num2" required id="num2" type="number">
          </div>
          <div class="col"><p> Resultado: {{ getOperacoes() }}</p></div>
        </div>
       </form>
</template>