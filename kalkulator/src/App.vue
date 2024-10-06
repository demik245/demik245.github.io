<script setup>
import { ref } from 'vue';

const wynik = ref('');

const appendValue = (character) => {
  wynik.value = wynik.value + character;
};

const Clear = () => {
  wynik.value = '';
};

const Calculate = () => {
  try {
    wynik.value = eval(wynik.value).toString();
  } catch (e) {
    wynik.value = 'Error';
  }
};
</script>

<template>
  <div class="miejsce-na-wynik">{{ wynik }}</div>
  <p>
    <button type="button" @click="appendValue('7')">7</button>
    <button type="button" @click="appendValue('8')">8</button>
    <button type="button" @click="appendValue('9')">9</button>
    <button type="button" @click="appendValue('/')">/</button>
  </p>
  <p>
    <button type="button" @click="appendValue('4')">4</button>
    <button type="button" @click="appendValue('5')">5</button>
    <button type="button" @click="appendValue('6')">6</button>
    <button type="button" @click="appendValue('*')">*</button>
  </p>
  <p>
    <button type="button" @click="appendValue('1')">1</button>
    <button type="button" @click="appendValue('2')">2</button>
    <button type="button" @click="appendValue('3')">3</button>
    <button type="button" @click="appendValue('-')">-</button>
  </p>
  <p>
    <button type="button" @click="Clear">C</button>
    <button type="button" @click="appendValue('0')">0</button>
    <button type="button" @click="appendValue('.')">.</button>
    <button type="button" @click="appendValue('+')">+</button>
    <button type="button" @click="Calculate">=</button>
  </p>
</template>

<style scoped>
.miejsce-na-wynik {
  background-color: white;
  color: black;
  width: 150px;
  height: 50px;
  border: 2px solid #ddd;
  border-radius: 5px;
  padding: 10px;
  margin-bottom: 20px;
  text-align: right;
  font-size: 24px;
  box-sizing: border-box;
}
button {
  border: none;
  width: 30px;
  height: 30px;
  margin: 5px;
}
</style>