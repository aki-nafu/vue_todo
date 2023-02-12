<template>
  <div className="container is-fluid">
  <ToDoApp/>
  </div>
</template>

<script>
import ToDoApp from './components/ToDoApp.vue'
import 'bulma/css/bulma.css';

export default {
  name: 'App',
  components: {
    ToDoApp
  }
}
</script>

<style>
#app {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
