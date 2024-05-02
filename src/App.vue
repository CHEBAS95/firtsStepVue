<template>
  <div>
    <h1>¡Hola, Sebillas! Esto va a ser un desafío en {{ curso }}</h1>
    <p v-bind:style="carrer">
      Voy a ser experto en {{ carrera.join('-') }}.
      <br />
      {{ mensaje }}
    </p>
    <h2 v-bind:class="hard">Es difícil, pero lo lograré</h2>
    <button @click="saludo">Saludo</button>
  </div>
</template>

<style scoped>
  h1 {
    background-color: aqua;
    color: tomato;
  }
  .dificil {
    background-color: rgb(21, 195, 50);
    color: blue;
  }
  button {
    background-color: aqua;
    color: yellow;
  }
  button:hover {
    background-color: yellow;
    color: green;
  }
</style>

<script setup>
const curso = 'Vue';
const carrera = ['Vue', 'JS', 'React', 'SQL'];
const carrer = 'color:green;font-size:4em';
let mensaje = '';
const hard = 'dificil';

function saludo() {
  mensaje = '¡Hola, esto lo debo lograr y ganarle a todos los gonorreas!';
  alert(`¡Hola ${curso}! Este es mi primer framework. ¡Si no me mato, HP!`);
}
</script>
