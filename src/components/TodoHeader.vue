<script lang="ts" setup>
import { ref } from 'vue'

const emits = defineEmits<{
  addTodo: [string]
}>()

const todoText = ref('')
</script>

<template>
  <div class="header-box">
    <h1>Todo list</h1>

    <div class="header-actions-box">
      <input
        type="text"
        class="header-input"
        v-model="todoText"
        placeholder="Добавьте новую задачу!"
      />
      <button class="header-btn-add" @click="emits('addTodo', todoText)">
        +
      </button>
    </div>
  </div>
</template>

<style scoped>
.header-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  width: 400px;
  height: 140px;
  padding: 20px;
  box-shadow: 4px 8px 18px rgb(216, 216, 216);
  border-radius: 8px;
}

.header-actions-box {
  display: flex;
  gap: 12px;
  width: 100%;
}

.header-input {
  flex-grow: 1;
  padding: 6px;
}

.header-btn-add {
  width: 30px;
  height: 30px;
  font-size: 18px;
}
</style>
