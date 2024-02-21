<script setup>
    const props = defineProps(['operacoes', 'num1', 'num2'])
</script>

<template>
     <div class="col">
        <label for="operacoes">Operações:</label>
        <select @change="props.operacoes">
          <option value="somar">Somar</option>
          <option value="subtrair">Subtrair</option>
          <option value="dividir">Dividir</option>
          <option value="multiplicar">Multiplicar</option>
        </select>
    </div>
    <div class="row">
          <div class="col">
            <input @keyup="props.num1" required type="number" placeholder="Insira o numero 1">
          </div>
          <div class="col">
            <input @keyup="props.num2" required type="number" placeholder="Insira o numero 2">
          </div>
    </div>      
</template>