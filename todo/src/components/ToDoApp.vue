<template>
  <div id="app">
    <h1>Todoリスト</h1>
      <input v-model="todo.name"><br>
    <button @click="addTodo">追加</button>
    <ul>
      <li v-for="(todo, index) in todos" :key="todo">
        <input type="checkbox" @click="removeTodo(index)" >{{ todo.name }} 
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: {
        'name': name,
        'done': true
      },
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