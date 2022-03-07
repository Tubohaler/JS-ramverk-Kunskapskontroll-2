<script setup>
import Todo from './components/Todo.vue';
</script>

<template>
 <Todo />
 <!-- <img :class="background-img" alt="Background" src="./assets/background.jpeg" />
 <img :class="colorOverlay" alt="bakground overlay" src="./assets/background.jpeg" /> -->

</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: -25px;
  background-color: rgb(255, 255, 255);
}

.background-img {
  position: absolute;
  margin-left: 24%;
  height: 90%;
  object-fit: cover;
  overflow: hidden;
}

.colorOverlay {
  background: #000;
  width: 100vw;
  height: 100vh;
  position: absolute;
  opacity: 0.7;
  object-fit: cover;
}
</style>
