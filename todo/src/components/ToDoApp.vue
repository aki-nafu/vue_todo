<template>
  <div id="app" className="panel is-warning">
    <h1 className="panel-heading display">
      <img src="../Vue.png" width="20" height="20" align="center" /> ToDo
    </h1>
    <div className="panel-block">
      <input
        class="input"
        placeholder="Enter to add"
        v-model="todoName"
      /><br />
      <button class="button" @click="addTodo">Add</button>
    </div>
    <div className="panel-tabs">
      <a href="#" @click="changeFilter('ALL')">All</a>
      <a href="#" @click="changeFilter('TODO')">ToDo</a>
      <a href="#" @click="changeFilter('DONE')">Done</a>
    </div>
    <ToDoList :todos="todos" :filter="filter" @toggle-todo="handleToggleTodo" />
  </div>
</template>

<script>
import "bulma/css/bulma.css";
import ToDoList from "./ToDoList.vue";

export default {
  components: {
    ToDoList,
  },
  data() {
    return {
      todoName: "",
      todos: [],
      filter: false,
    };
  },
  methods: {
    addTodo() {
      if (this.todoName == "") return;
      this.todos.push({ name: this.todoName, isCompleted: false });
      this.todoName = "";
    },
    changeFilter(value) {
      switch (value) {
        case "ALL":
          this.filter = null;
          break;
        case "TODO":
          this.filter = false;
          break;
        case "DONE":
          this.filter = true;
          break;
        default:
          break;
      }
    },
    handleToggleTodo(index) {
      // `todos`配列の要素を更新
      this.todos[index].isCompleted = !this.todos[index].isCompleted;
    },
  },
};
</script>

<style></style>
