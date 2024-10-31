<script setup lang="ts">
import type { Todo } from '@/App.vue'

const props = defineProps<{
  todos: Todo[]
}>()
</script>

<template>
  <TodoItem />
</template>
