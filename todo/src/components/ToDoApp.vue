<template>
  <div id="app">
    <h1>Todoリスト</h1>
      <input v-model="todo"><br>
    <button @click="addTodo">追加</button>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">{{ todo }} <span @click="removeTodo(index)">X</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: '',
      todos:[]
    }
  },
  methods: {
    addTodo() {
      this.todos.push(this.todo)
      this.todo = ''
    },
    removeTodo(index) {
      this.todos.splice(index, 1)
    }
  }
}
</script>

<style>
</style>