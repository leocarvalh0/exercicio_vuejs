<script setup>
import { reactive } from 'vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

  const estado = reactive({
    num1: 0,
    num2: 0,
    filtro: 'selecione',
  })

  const somar = () => {
    const resultado = Number(estado.num1) + Number(estado.num2);
    return resultado;
  }

  const subtrair = () => {
    const resultado = Number(estado.num1) - Number(estado.num2);
    return resultado;
  }

  const multiplicar = () => {
    const resultado = Number(estado.num1) * Number(estado.num2);
    return resultado;
  }

  const dividir = () => {
    const resultado = Number(estado.num1) / Number(estado.num2);
    return resultado;
  }

  const trocarFiltro = () => {
    const { filtro } = estado;

    switch (filtro) {
      case 'somar':
        return somar();
      case 'subtrair':
        return subtrair();
      case 'multiplicar':
        return multiplicar();
      default:
        return dividir();
    }
  }

</script>

<template>
  <div class="container">
    <h1>Calcule</h1>
    <Formulario :retorna-num1="evento => estado.num1 = evento.target.value" :retorna-num2="evento => estado.num2 = evento.target.value" :trocar-filtro="evento => estado.filtro = evento.target.value" />
    <Resultado :trocar-filtro="trocarFiltro()" :filtro="estado.filtro"/>
  </div>
</template>

<style scoped>
  .container {
    font-family: sans-serif;
    max-width: 400px;
    margin: 100px auto;
    background-color: #000;
    color: #fff;
    padding: 60px;
  }

  h1 {
    font-size: 40px;
    margin-bottom: 40px;
  }
</style>