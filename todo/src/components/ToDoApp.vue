<template>
  <div id="app" className="panel is-warning">
    <h1 className="panel-heading">
      ToDo
    </h1>
    <div className="panel-block">
      <input class="input" v-model="todoName" ><br>
      <button class="button" @click="addTodo">Add</button>
    </div>
    <div className="panel-tabs">
      <a href="#" @click="changeFilter('ALL') ">All</a>
      <a href="#" @click="changeFilter('TODO')">Todo</a>
      <a href="#" @click="changeFilter('DONE')">Done</a>
    </div>
    <ul>
      <template v-for="(todo, index) in todos">
        <label className="panel-block" v-if="filter === null || filter === todo.isCompleted" :key="todo">
          <input type="checkbox" v-model="todo.isCompleted" @click="removeTodo(index)">{{ todo.name }}
        </label>
      </template>
    </ul>
  </div>
</template>

<script>
import 'bulma/css/bulma.css';
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