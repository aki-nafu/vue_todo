<template>
  <div id="app">
    <h1>Todoリスト</h1>
    <div>
      <a href="#" @click="changeFilter('ALL') ">ALL</a>
      <a href="#" @click="changeFilter('TODO')">TODO</a>
      <a href="#" @click="changeFilter('DONE')">DONE</a>
    </div>
    <input v-model="todoName"><br>
    <button @click="addTodo">追加</button>
    <ul>
      <template v-for="(todo, index) in todos">
        <li v-if="filter === null || filter === todo.isCompleted" :key="todo">
          <input type="checkbox" v-model="todo.isCompleted" @click="removeTodo(index)">{{ todo.name }}
        </li>
      </template>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todoName:'',
      todos:[],
      filter: false
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
    },
    changeFilter(value) {
      switch (value) {
        case 'ALL':
          this.filter = null;
          break;
        case 'TODO':
          this.filter = false;
          break;
        case 'DONE':
          this.filter = true;
          break;
        default:
          break;
      }   
    }
  }
}
</script>

<style>
</style>