<script setup>
import css from "./App.module.css"
import {ref} from "vue";

const text = ref("")
const cards = [
  {id: 0, data: "Lorem"},
  {id: 1, data: "Ipsum"},
  {id: 2, data: "Dolor"},
  {id: 3, data: "Sit"},
  {id: 4, data: "Amet"},
  {id: 5, data: "Lorem21"},
  {id: 6, data: "!Ipsum_!"},
  {id: 7, data: "__Dolor_"},
  {id: 8, data: "%Sit%"},
  {id: 9, data: "##Amet#"},
]
</script>

<template>
  <div :class="css.data">
    <span style="margin-right: 10px">Search:</span>
    <input type="text" v-model="text">
  </div>

  <template v-for="card in cards" :key="card.id">
    <div :class="[css.card]" v-if="card.data.includes(text)">
      {{ card.id }}: {{ card.data }}
    </div>
  </template>
</template>
