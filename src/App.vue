<template>
  <div class="one">
    <h1>¡Hola, Sebillas! Esto va a ser un desafío en {{ curso }}</h1>
    <p v-bind:style="carrer">
      Voy a ser experto en {{ carrera.join(',') }}.
      <br />
      {{ mensaje }}
    </p>
    <h2 v-bind:class="hard">Es difícil, .pero lo lograré</h2>
    <button @click="saludo()">Saludo</button>
  </div>
  <hr>
  <div class="second">
    <h2>clase reactiva</h2>
    <button @click="sumar()">
      sumar
    </button>
    <span v-bind:class="color">{{ contandor }}</span>
    <button v-on:click="restar()">
      restar
    </button>
    <p v-show="quitar">sumale un poco.</p>
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

.one>button {
  background-color: aqua;
  color: yellow;
}

button:hover {
  background-color: yellow;
  color: green;
}

h2 {
  color: chartreuse;
}

.second {
  text-align: center;
  background-color: black;
  display: flex;
  align-items: center;
  justify-content: center;
}

.green {
  color: green;
}

.red {
  color: red;
}
.black{
  color: rgb(132, 15, 178);
}
p{
  color: aliceblue;
}
span {
  background-color: rgb(244, 236, 243);
  width: 10em;
  margin: 10px;
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

import { ref } from "vue";
const contandor = ref(0);
const color = ref ("black");
const quitar = ref (false);

const sumar = () => {
  contandor.value++;
 contandor.value>=8 ? color.value="green" : color.value="black"
 if (contandor.value >= 0) {
    quitar.value=(false)
  }
}
const restar = () => {
  contandor.value--;
  if (contandor.value < 0) {
    color.value = "red";
  }
  if (contandor.value <= -4) {
    quitar.value=(true)
  }
}

</script>
