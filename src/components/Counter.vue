<script setup>
import {ref, watchEffect} from "vue";

const counter = ref(0)
const date = ref(new Date().toLocaleTimeString())

watchEffect(() => {
  setInterval(() => {
    date.value = new Date().toLocaleTimeString()
  }, 1000)
})
</script>

<template>
  <button @click="counter++">+</button>
  <button @click="counter--">-</button>
  <h1>Счетчик: {{ counter }}</h1>
  <h1>Время: {{ date }}</h1>
</template>

<style scoped>
  h1 {
    font-family: monospace;
  }
  button {
    background-color: black;
    color: white;
    border-radius: 10px;
    border: 2px solid grey;
    height: 30px;
    width: 30px;
  }
</style>