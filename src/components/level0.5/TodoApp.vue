<script setup>
import { ref } from 'vue';

const newTodo = ref([]);

function addTodo() {
  todos.value.push({
    id: 2,
    text: newTodo.value,
    completed: false,
  });
}

const todos = ref([
  {
    id: 1,
    text: 'Learn Vue.js 3',
    completed: false,
  },
]);
</script>
<template>
  <div
    v-for="i in todos"
    data-test="todo"
    :key="i"
    :class="{ completed: i.completed }"
  >
    <input type="checkbox" v-model="i.completed" data-test="todo-checkbox" />
    {{ i.text }}
  </div>
  <input type="text" data-test="new-todo-input" v-model="newTodo" />
  <button data-test="new-todo-btn" @click="addTodo"></button>
</template>
