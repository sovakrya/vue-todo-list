<script setup lang="ts">
import type { Todo } from '@/App.vue'

const props = defineProps<{
  todo: Todo
}>()

const emits = defineEmits<{
  removeTodo: []
  doneTodo: []
}>()
</script>

<template>
  <div class="todo-item-box" :class="{ 'cheked-todo-bg': props.todo.isDone }">
    <div class="todo-item-text-box">
      <input
        type="checkbox"
        @change="emits('doneTodo')"
        v-if="!props.todo.isDone"
      />
      <span :class="{ 'cheked-todo-text': props.todo.isDone }">{{
        props.todo.todoText
      }}</span>
    </div>
    <button class="todo-item-remove-btn" @click="emits('removeTodo')">X</button>
  </div>
</template>

<style scoped>
.todo-item-box {
  display: flex;
  align-items: center;
  padding: 12px;
  gap: 8px;
  box-shadow: 4px 8px 10px rgb(216, 216, 216);
  width: 400px;
  height: 50px;
  border-radius: 8px;
}

.todo-item-text-box {
  display: flex;
  flex-grow: 1;
  gap: 8px;
}

.todo-item-remove-btn {
  font-size: 16px;
  width: 24px;
}

.cheked-todo-bg {
  background-color: rgb(172, 172, 172);
}
.cheked-todo-text {
  text-decoration: line-through;
}
</style>
