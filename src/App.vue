<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  filtro: 'soma',
  valor1: '',
  valor2: '',
  resultado: ''
})

const soma = () => {
  const resultadoSoma = estado.valor1 + estado.valor2
  estado.resultado = resultadoSoma;
  return estado.resultado
}

const subtracao = () => {
  const resultadoSubtracao = estado.valor1 - estado.valor2
  estado.resultado = resultadoSubtracao;
  return estado.resultado
}

const multiplicacao = () => {
  const resultadoMultiplicacao = estado.valor1 * estado.valor2
  estado.resultado = resultadoMultiplicacao
  return estado.resultado
}

const divisao = () => {
  const resultadoDivisao = estado.valor1 / estado.valor2
  estado.resultado = resultadoDivisao
  return estado.resultado
}

</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario :valorUm="event => estado.valor1 = Number(event.target.value)"
      :valorDois="event => estado.valor2 = Number(event.target.value)" :filtro="estado.filtro"
      :selecionaFiltro="event => estado.filtro = event.target.value" />
    <Resultado :filtro="estado.filtro" :funcaoSoma="soma()" :funcaoSub="subtracao()" :funcaoMult="multiplicacao()"
      :funcaoDiv="divisao()" />
  </div>
</template>

<style scoped></style> 
