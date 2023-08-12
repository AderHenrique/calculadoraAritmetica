<script setup>
const props = defineProps(['valorUm', 'valorDois', 'filtro', 'selecionaFiltro'])
</script>

<template>
   <form>
      <div class="row">
         <div class="col-md-4">
            <input @keyup="props.valorUm" type="number" class="form-control" placeholder="Insira o primeiro valor">
         </div>
         <div class="col-md-4">
            <select @change="props.selecionaFiltro" class="form-control">
               <option value="soma">Soma</option>
               <option value="subtracao">Subtracao</option>
               <option value="multiplicacao">Multiplicação</option>
               <option value="divisao">Divisão</option>
            </select>
         </div>
         <div class="col-md-4">
            <input @keyup="props.valorDois" type="number" class="form-control" placeholder="Insira o segundo valor">
         </div>

      </div>
   </form>
</template>