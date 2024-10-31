<script setup lang="ts">
import type { Todo } from '@/App.vue'
import TodoItem from './TodoItem.vue'

const emits = defineEmits<{
  deleteTodo: [number]
  doneTodo: [number]
}>()

const props = defineProps<{
  todos: Todo[]
}>()
</script>

<template>
  <TodoItem
    v-for="(todo, idx) in props.todos"
    :key="todo.id"
    :todo
    @remove-todo="emits('deleteTodo', idx)"
    @done-todo="emits('doneTodo', idx)"
  />
</template>
