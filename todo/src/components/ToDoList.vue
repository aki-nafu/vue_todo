<template>
  <ul>
    <template v-for="(todo, index) in todos">
      <label
        class="panel-block"
        v-if="filter === null || filter === todo.isCompleted"
        :key="todo"
      >
        <input
          type="checkbox"
          :checked="todo.isCompleted"
          @change="toggleTodo(index)"
        />
        {{ todo.name }}
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
    toggleTodo(index) {
      this.$emit("toggle-todo", index);
    },
  },
};
</script>

<style></style>
