<template>
  <div id="app">
    <h1>Todoリスト</h1>
      <input v-model="todoName"><br>
    <button @click="addTodo">追加</button>
    <ul>
      <li v-for="(todo, index) in todos" :key="todo">
        <div v-show="!todo.isCompleted">
          <input type="checkbox" v-model="todo.isCompleted" @click="removeTodo(index)" >{{ todo.name }} 
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todoName:'',
      todos:[]
    }
  },
  methods: {
    addTodo() {
      if (this.todoName == '') return;
      this.todos.push({name: this.todoName, isCompleted: false})
      this.todoName = ''
    },
    removeTodo(index) {
      this.todos[index].isCompleted = true
    }
    
  }
}
</script>

<style>
</style>