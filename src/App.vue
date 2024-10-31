<script setup lang="ts">
import TodoHeader from './components/TodoHeader.vue'
</script>

<template>
  <main class="main-box">
    <TodoHeader />
  </main>
</template>

<style scoped>
.main-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 34px;
}
</style>
