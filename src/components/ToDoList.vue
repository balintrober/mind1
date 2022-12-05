<template>
  <input type="text" v-model="todo" @change="addItem(todo)" placeholder="Új feladat megadása">
  <!-- <ul>
    <li v-for="todo in todoList">{{ todo }}</li>
  </ul> -->
  
  <table v-if="todoList.size">
    <tr v-for="todo in todoList">
      <td>{{todo}}</td>
      <td><span class="btn btn-danger" @click = "deleteItem(todo)">Törlés</span></td>
    </tr>
  </table>
  <h3 class="text-success" v-else="todoList.size">Mára nincs több teendő!</h3>
</template>

<script setup>
import { ref } from 'vue';
const todo = ref(null);
const todoList = ref(new Set());

function addItem(t){
  todoList.value.add(t);
  todo.value = '';
}
function deleteItem(t){
  todoList.value.delete(t); //halmaz elemének törlése
}

</script>

<style scoped>
  
</style>