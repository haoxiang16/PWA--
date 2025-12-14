<template>
  <div id="app">
    <header>
      <h1>📝 待辦事項</h1>
      <p class="subtitle">簡易 PWA 應用</p>
    </header>
    <main>
      <TodoList />
    </main>
    <footer>
      <p>離線可用 · 可安裝到主畫面</p>
    </footer>
  </div>
</template>

<script setup>
import TodoList from './components/TodoList.vue'
</script>

