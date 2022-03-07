<script setup>
import { ref } from "vue";

const todoEmpty = ref("");
const addNewTodos = ref([{ title: "", complete: false }]);
const deleteTodo = ref([]);
function pushingTodos() {
  addNewTodos.value.push({
    title: todoEmpty.value,
    complete: false,
  });
  todoEmpty.value = "";
}

function deleteActivity(index) {
  addNewTodos.value.splice(index, 1);
}
</script>

<template>
  <h1>David's Todo-Shite!</h1>
  <label>Do something!</label>
  <div>
    <input name="newTodo" v-model="todoEmpty" />
    <button @click="pushingTodos">Add</button>
    <button @click="deleteTodo(index)">Kill</button>
  </div>

  <ul :class="{ listItems }">
    <li v-for="(addNewTodos, index) in addNewTodos" :key="index">
      {{ addNewTodos.title }}
    </li>
  </ul>
</template>




<style>
.listItems {
  text-decoration: none;
}

.done {
  text-decoration: line-through;
}
</style>