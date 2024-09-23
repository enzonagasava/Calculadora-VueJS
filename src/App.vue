<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';


const estado = reactive({
  filtro: 'Adição',
  numTemp1: 0,
  numTemp2: 0,
})


const somaNum = ({ numTemp1, numTemp2} = estado) =>
{return  (numTemp1 + numTemp2)};

const subtracaoNum = ({ numTemp1, numTemp2} = estado )=> 
{ return  (numTemp1 - numTemp2)};

const multiplicacaoNum = ({ numTemp1, numTemp2} = estado) => 
{ return  (numTemp1 * numTemp2)};

const divisaoNum = ({ numTemp1, numTemp2} = estado ) => 
{return  (numTemp1 / numTemp2)};


const getResultado = () => {
  const {numTemp1, numTemp2, filtro} = estado

  if((numTemp1, numTemp2)){
    switch (filtro){
    case 'Subtração':
      return subtracaoNum();
    case 'Multiplicação':
      return multiplicacaoNum();
    case 'Divisão':
      return divisaoNum();
    case 'Adição':
      return somaNum();
  }
  }
}

</script>

<template>
  <div class="container">
    <Cabecalho/>
    <Formulario :num1="evento => estado.numTemp1 = Number(evento.target.value)" :num2="evento => estado.numTemp2 = Number(evento.target.value)" :filtro="evento => estado.filtro = evento.target.value"/>
    <Resultado :resultado="getResultado()"/>
</div>
</template>

<style scoped>
</style>
