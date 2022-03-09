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

function completedTodos(addNewTodos) {
  index.value.forEach((addNewTodos, index) => {
    if (index === addNewTodos) {
      addNewTodos.complete = !addNewTodos.complete;
    }
  });
}
</script>

<template>
  <h1 :class="title">David's Todo-Shite!</h1>
  <section class="background">
    <img
      class="backgroundImg"
      alt="Background"
      src="../assets/background.jpeg"
    />
  </section>

  <label>Do something!</label>
  <div class="">
    <input name="newTodo" v-model="todoEmpty" />
    <button @click="pushingTodos">Add</button>
    <button @click="deleteActivity(index)">Kill</button>
  </div>

  <div class="list">
    <div
      v-for="(addNewTodos, index) in addNewTodos"
      class="listItem"
      :key="index"
    >
      <span :class="{ completed: addNewTodos.complete }"
        >{{ addNewTodos.title }}
      </span>
      {{ addNewTodos.title }}
      <input
        :class="{ complete: index.complete }"
        @click="completedTodos(index)"
        type="checkbox"
      />
    </div>
  </div>
</template>

<style>
html {
  background-color: rgb(0, 0, 0);
}

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
}

.background {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
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