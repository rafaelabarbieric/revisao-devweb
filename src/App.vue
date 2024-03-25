<script setup>

import { ref } from 'vue'

const titulo = ref('Titulo')

</script>

<template>

  <h1>{{ titulo }}</h1>

  <div class="container">

    <div class="formulario">

      <h2>Formulario</h2>
      <input type="text" v-model="titulo"/>

    </div>

    <div class="resultado">

      <h2>Resultado</h2>

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

</style>
