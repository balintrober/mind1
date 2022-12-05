<template>
  <input type="text" v-model="todo" @change="addItem(todo)" placeholder="Új feladat megadása">
  <ul>
    <li v-for="todo in todoList">{{ todo }}</li>
  </ul>
</template>

<script setup>
import { ref } from 'vue';
const todo = ref(null);
const todoList = ref([]);

function addItem(t){
  todoList.value.push(t);
  todo.value = '';
}
</script>

<style scoped>
  
</style>