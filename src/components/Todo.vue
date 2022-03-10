<script setup>
import { ref } from "vue";

const todoEmpty = ref("");
const addNewTodos = ref([]);
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

function completedTodos(addNewTodos) {
  index.value.forEach((addNewTodos, index) => {
    if (index === addNewTodos) {
      addNewTodos.complete = !addNewTodos.complete;
    }
  });
}
</script>

<template>
  <h1 class="background">David's Todo-Shite!</h1>

  <label>Do something!</label>
  <div class="buttonChoices">
    <input name="newTodo" v-model="todoEmpty" />
    <button @click="pushingTodos">Add</button>
    <button @click="deleteActivity(index)">Kill</button>
  </div>

  <div class="list">
    <div
      v-for="(todo, index) in addNewTodos"
      class="listItem"
      :key="index"
    >
      <span :class="{ completed: todo.complete }"
        >{{ todo.title }}
      </span>
      <input
        :class="{ complete: index.complete }"
        @click="completedTodos(index)"
        type="checkbox"
      />
    </div>
  </div>
</template>

<style>

label {
  margin-left: -118px;
}

.list {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.listItem {
  height: 25px;
  width: 223px;
  margin-top: 16px;
  border: 3px solid rgb(255, 255, 255);
}

input {
  padding: 0px;

}

button {
  border: 0px;
  background-color: orange;
  margin: 0.1rem;
}

.background {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  z-index: 0;
}

.backgroundImg {
  height: 75vh;
  position: absolute;
  opacity: 0.1;
  margin-top: -2rem;
}

/* .title {
  font-family: 'MedievalSharp', cursive;
  color: #ffffff;
  z-index: 2;
  margin: 0.2rem;
  margin-top: 8rem;
  padding: 0rem;
} */

.completed {
  text-decoration: line-through;
}
</style>