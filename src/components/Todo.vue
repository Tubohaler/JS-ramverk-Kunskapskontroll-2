<script setup>
import { ref } from "vue";

const todoEmpty = ref("");
const addNewTodos = ref([{ title:"", complete: false }]);
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
  })
}
  

</script>

<template>
  <h1 :class="title" >David's Todo-Shite!</h1>
  
  <img :class="colorOverlay" alt="bakground overlay" src="../assets/background.jpeg" />
  <img :class="background-img" alt="Background" src="../assets/background.jpeg" />
  
  <label>Do something!</label>
  <div class="list">
    <input name="newTodo" v-model="todoEmpty" />
    <button @click="pushingTodos">Add</button>
    <button @click="deleteActivity(index)">Kill</button>
  </div>

  <div class="list">
    <div v-for="(addNewTodos, index) in addNewTodos" :class="listItem" :key="index" >
        <span :class="{ completed: addNewTodos.complete }" >{{addNewTodos.title}} </span>
      {{ addNewTodos.title }}
      <input :class="{complete: index.complete }" @click="completedTodos(index)" type="checkbox"/>
    </div>
  </div>
</template>

<style>
html {
    background-color: #000;
}

.list {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.listItem {
   height: 60px;
   width: 240px;
   margin-top: 12px;
   border: 3px solid rgb(255, 255, 255);

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

/* .background-img {
  position: absolute;
  margin-left: 24%;
  height: 90%;
  object-fit: cover;
  overflow: hidden;
  z-index: 0;
}

.colorOverlay {
  background: #000;
  width: 100vw;
  height: 100vh;
  position: absolute;
  opacity: 0.7;
  object-fit: cover;
  z-index: 1;
} */
</style>