<script setup lang="ts">
import {ref} from "vue";

const msg = 'vue js'
const counter = ref(0)
const currentValues = ref<Array<number>>([])

const incrementCount = () => counter.value++

const decrementCount = () => counter.value--

const resetCount = () => counter.value = 0

const addValue = () => {
  if (currentValues.value.find(n => n === counter.value)) return
  currentValues.value.push(counter.value)
}

</script>

<template>
  <h1>Hi {{msg}}</h1>
  <h2>counter {{counter}}</h2>
  <button @click="incrementCount">Increment</button>
  <button @click="decrementCount">Decrement</button>
  <button @click="resetCount">Reset</button>
  <button @click="addValue">Add</button>
  <ul>
    <li v-for="value in currentValues" :key="value">{{value}}</li>
  </ul>
</template>

<style>

</style>