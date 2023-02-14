<template>
  <ul>
    <template v-for="(todo, index) in todos">
      <label className="panel-block" v-if="filter === null || filter === todo.isCompleted" :key="todo">
        <input type="checkbox" v-model="todo.isCompleted" @click="removeTodo(index)">{{ todo.name }}
      </label>
    </template>
  </ul>
</template>

<script>
export default {
  props: {
    todos: Array,
    filter: Boolean,
  },
  methods: {
    removeTodo (index) {
      this.todos[index].isCompleted = true
    },
  },
}
</script>