<template>
  <div class="flex flex-col h-screen maw-w-md mx-auto justify-center align-center ">
    <div class="w-3/5  mb-5 mx-auto">
      <row-word v-for="(guess, i) in state.guesses" :key="i" :value="guess" :solution="state.solution" :submitted="i<state.currentGuessIndex"/>
    </div>
    <SimpleKeyboard @onKeyPress="handleInput"/>
  </div>
  </template>

<script setup>
import { reactive,onMounted } from 'vue';
import SimpleKeyboard from './components/SimpleKeyboard.vue';
import RowWord from './components/RowWord.vue';

const state = reactive({
  solution: "books",
  guesses: ["","","","","",""],
  currentGuessIndex: 0,
});
const handleInput = (key)=>{
  console.log(key);
}
onMounted(()=>{
  window.addEventListener("keyup",(e)=>{
    e.preventDefault();
    let key =
     e.keyCode == 13 
      ? "{enter}"
      :e.keyCode ==8
      ? "{bksp}"
      :String.fromCharCode(e.keyCode).toLocaleLowerCase();
    handleInput(key)
  });
})
</script>

<style>

</style>
