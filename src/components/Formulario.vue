<script setup>
const props = defineProps(['num1', 'num2', 'operacoes', 'resultado'])
</script>

<template>
    <form>
    <input class="ponta" @change="props.num1" type="number" placeholder="1º numero">
    <input class="centro" @change="props.num2" type="number" placeholder="2º numero">
    <div>
      <select @change="props.operacoes">
        <option value="soma">Soma</option>
        <option value="subtracao">Subtração</option>
        <option value="divisao">Divisão</option>
        <option value="multiplicacao">Multiplicação</option>
      </select>
    </div>
  </form>
  <h3>Resultado<br> {{ props.resultado }}</h3>
</template>

<style scoped>


form{
  display:flex;
  justify-content: center;
  padding: 25px 0;
}

input{
  margin-bottom: 10px;
  font-size: 18px;
  width: 100px;
  height: 40px;
  border-radius: 20px;
  border-color: transparent;
}

select{
  height: 40px;
  text-align: center;
  border-radius: 20px;
  border-color: transparent;
  height: 45px;
  width: 110px;
  margin-bottom: 10px;
}

option{
  font-size: 20px;
}

h3{
  text-align: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #fff;
  font-size: 40px;
}

.ponta{
  text-align: center;
}

.centro{
  margin: 0 20px;
  text-align: center;
}
</style>