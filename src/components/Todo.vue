<script setup>
import { ref } from 'vue';

const todoEmpty = ref("")
const addNewTodo = ref([
    {title: "Sporta mer", complete: false }, 
    {title: "Sporta mer", complete: false },
])
const deleteTodo = ref([])
;

</script>

<template>
  <h1>David's Todo-Shite!</h1>
  <label>Do something!</label>
  <div>
    <input name="newTodo" v-model="todoEmpty" />
    <button @click="addNewTodo" >Add</button>
    <button @click="deleteTodo">Kill</button>
  </div>

  <ul>
    <li v-for="(todoEmpty, index) in todoEmpty" :key="index">{{addNewTodo.title}}</li>
  </ul>
</template>




<style>
</style>