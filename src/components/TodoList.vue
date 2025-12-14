<template>
  <div class="todo-container">
    <div class="todo-input-section">
      <input
        v-model="newTodo"
        @keyup.enter="addTodo"
        type="text"
        placeholder="輸入待辦事項..."
        class="todo-input"
      />
      <button @click="addTodo" class="add-btn" :disabled="!newTodo.trim()">
        新增
      </button>
    </div>

    <div class="todo-stats">
      <span>總共: {{ todos.length }}</span>
      <span>已完成: {{ completedCount }}</span>
      <span>未完成: {{ todos.length - completedCount }}</span>
    </div>

    <div class="todo-list">
      <div
        v-for="todo in todos"
        :key="todo.id"
        class="todo-item"
        :class="{ completed: todo.completed }"
      >
        <input
          type="checkbox"
          :checked="todo.completed"
          @change="toggleTodo(todo.id)"
          class="todo-checkbox"
        />
        <span class="todo-text" @click="toggleTodo(todo.id)">{{ todo.text }}</span>
        <button @click="deleteTodo(todo.id)" class="delete-btn">刪除</button>
      </div>
      <div v-if="todos.length === 0" class="empty-state">
        <p>還沒有待辦事項，開始新增吧！</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, watch } from 'vue'

const STORAGE_KEY = 'vue-pwa-todos'

const newTodo = ref('')
const todos = ref([])

const completedCount = computed(() => {
  return todos.value.filter(todo => todo.completed).length
})

// 從 localStorage 載入數據
const loadTodos = () => {
  const stored = localStorage.getItem(STORAGE_KEY)
  if (stored) {
    try {
      todos.value = JSON.parse(stored)
    } catch (e) {
      console.error('載入待辦事項失敗:', e)
      todos.value = []
    }
  }
}

// 保存到 localStorage
const saveTodos = () => {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(todos.value))
}

// 添加待辦事項
const addTodo = () => {
  const text = newTodo.value.trim()
  if (text) {
    todos.value.push({
      id: Date.now(),
      text: text,
      completed: false,
      createdAt: new Date().toISOString()
    })
    newTodo.value = ''
    saveTodos()
  }
}

// 切換完成狀態
const toggleTodo = (id) => {
  const todo = todos.value.find(t => t.id === id)
  if (todo) {
    todo.completed = !todo.completed
    saveTodos()
  }
}

// 刪除待辦事項
const deleteTodo = (id) => {
  todos.value = todos.value.filter(t => t.id !== id)
  saveTodos()
}

// 監聽 todos 變化並保存
watch(todos, saveTodos, { deep: true })

// 組件掛載時載入數據
onMounted(() => {
  loadTodos()
})
</script>

<style scoped>
.todo-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.todo-input-section {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.todo-input {
  flex: 1;
  padding: 12px 16px;
  font-size: 16px;
  border: 2px solid #e5e7eb;
  border-radius: 8px;
  outline: none;
  transition: border-color 0.3s;
}

.todo-input:focus {
  border-color: #4f46e5;
}

.add-btn {
  padding: 12px 24px;
  font-size: 16px;
  font-weight: 600;
  color: white;
  background: #4f46e5;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s;
}

.add-btn:hover:not(:disabled) {
  background: #4338ca;
}

.add-btn:disabled {
  background: #9ca3af;
  cursor: not-allowed;
}

.todo-stats {
  display: flex;
  gap: 16px;
  margin-bottom: 20px;
  padding: 12px;
  background: #f3f4f6;
  border-radius: 8px;
  font-size: 14px;
  color: #6b7280;
}

.todo-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.todo-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 16px;
  background: white;
  border: 2px solid #e5e7eb;
  border-radius: 8px;
  transition: all 0.3s;
}

.todo-item:hover {
  border-color: #4f46e5;
  box-shadow: 0 2px 8px rgba(79, 70, 229, 0.1);
}

.todo-item.completed {
  opacity: 0.7;
  background: #f9fafb;
}

.todo-checkbox {
  width: 20px;
  height: 20px;
  cursor: pointer;
  accent-color: #4f46e5;
}

.todo-text {
  flex: 1;
  font-size: 16px;
  cursor: pointer;
  user-select: none;
  transition: text-decoration 0.3s;
}

.todo-item.completed .todo-text {
  text-decoration: line-through;
  color: #9ca3af;
}

.delete-btn {
  padding: 8px 16px;
  font-size: 14px;
  color: #ef4444;
  background: transparent;
  border: 1px solid #ef4444;
  border-radius: 6px;
  cursor: pointer;
  transition: all 0.3s;
}

.delete-btn:hover {
  background: #ef4444;
  color: white;
}

.empty-state {
  text-align: center;
  padding: 40px 20px;
  color: #9ca3af;
}

.empty-state p {
  font-size: 16px;
}
</style>

