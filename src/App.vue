<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';

  const estado = reactive({
    operacao: 'soma',
    num1:0,
    num2:0,
  })

  const soma = ({ num1, num2} = estado) =>{
    return num1 + num2};

  const subtracao = ({ num1, num2} = estado) =>{
    return num1 - num2};

  const divisao = ({ num1, num2} = estado) =>{
    return num1 / num2};

  const multiplicacao = ({ num1, num2} = estado) =>{
    return num1 * num2};

  const Calculo = () => {
    const {operacao, num1, num2} = estado;

    switch(operacao){
      case "soma":
        return soma();
      case "subtracao":
        return subtracao();
      case "divisao":
        return divisao();
      case "multiplicacao":
        return multiplicacao();
    }
  }

</script>

<template>
  <body>
    <div class="container">
    <Cabecalho/>
    <Formulario 
    :num1="evento => estado.num1 =Number (evento.target.value)"
    :num2="evento => estado.num2 =Number (evento.target.value)"
    :operacoes="evento => estado.operacao= evento.target.value"
    :resultado="Calculo()"
    />
  </div>
  </body>
</template>

<style scoped>

template{
  display: flex;
  justify-content: center;
  justify-items: center;
}

body{
  width: auto;
  height: auto;
}

</style>
