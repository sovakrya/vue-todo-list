<script setup lang="ts">
import { ref } from 'vue'
import TodoHeader from './components/TodoHeader.vue'
import TodoList from './components/TodoList.vue'

export type Todo = {
  id: number
  todoText: string
  isDone: boolean
}

const todos = ref<Todo[]>([])
let todoId = 1
function addNewTodo(todoText: string) {
  if (!todos.value.length) {
    todos.value.push({
      id: todoId,
      todoText,
      isDone: false,
    })
  } else {
    todoId += 1
    todos.value.push({
      id: todoId,
      todoText,
      isDone: false,
    })
  }
}

function removeTodo(idx: number) {
  todos.value.splice(idx, 1)
}
</script>

<template>
  <main class="main-box">
    <TodoHeader @add-todo="addNewTodo" />
    <TodoList :todos @delete-todo="removeTodo" />
  </main>
</template>

<style scoped>
.main-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 34px;
  gap: 30px;
}
</style>
