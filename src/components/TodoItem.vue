<script setup lang="ts">
import type { Todo } from '@/App.vue'

const props = defineProps<{
  todo: Todo
}>()
</script>

<template>
  <div>
    <input type="checkbox" />
    <span>{{ todo.todoText }}</span>
    <button>X</button>
  </div>
</template>

<style scoped>
.todo-item-box {
}
</style>
