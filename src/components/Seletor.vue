<script setup>
    const props = defineProps(['operation'])
</script>

<template>
     <div class="col">
        <label for="operation">Operações:</label>
        <select id="operation" class="operation" v-model="props.operation">
          <option value="somar">Somar</option>
          <option value="subtrair">Subtrair</option>
          <option value="dividir">Dividir</option>
          <option value="multiplicar">Multiplicar</option>
        </select>
    </div>
</template>