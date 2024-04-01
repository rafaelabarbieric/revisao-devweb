<script setup>

import { reactive, ref } from 'vue'

const titulo = ref('Titulo')

const mostraResultado = ref(false)

const produto = reactive({
  nome: '',
  preco: 0,
  quantidade: 0,
  categoria: []
})

function formatarPreco(preco) {
  return `R$ ${preco.toFixed(2).replace(".",",")}`
}

</script>

<template>

  <h1>{{ titulo }}</h1>

  <div class="container">

    <div class="formulario">

      <h2>Formulario</h2>
      <input type="text" v-model="titulo"/>

      <form @submit.prevent="mostraResultado = !mostraResultado">

        <div class="row">
          <label for="">Nome:</label>
          <input type="text" v-model="produto.nome" required>
        </div>

        <div class="row">
          <label for="">Preço:</label>
          <input type="number" v-model="produto.preco">
        </div> 

        <div class="row">
          <label for="">Quantidade:</label>
          <input type="number" v-model="produto.quantidade">
        </div> 

        <button type="submit">Mostrar</button>

      </form>

    </div>

    <div v-if="mostraResultado" class="resultado">

      <h2>Resultado</h2>
      <p>Nome: {{ produto.nome }}</p>
      <p>Preço: {{ formatarPreco(produto.preco) }}</p>
      <p>Quantidade: {{ produto.quantidade }}</p>
      <p>Categoria: {{ produto.categoria }}</p>

    </div>

  </div>
  
</template>

<style scoped>

.container{
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 1.5rem;
  width: 100vw;
}

.formulario,
.resultado{
  width: 45%;
  border-radius: 10px;
  padding: 10px;
}

.formulario{
  background-color: rgb(118, 118, 233);
}

.resultado{
  background-color: rgb(170, 111, 224);
}

.formulario .row{
  margin: 10px 20px;
  width: 70%;
  display: flex;
  justify-content: space-between;
}

</style>
