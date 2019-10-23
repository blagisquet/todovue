<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <Todolist :todos="todos" />
      </div>
    </div>
  </div>
</template>

<script>
import Todolist from "@/components/Todolist";

export default {
  name: "app",
  components: {
    Todolist
  },
  data() {
    return {
      todos: [
        {
          _id: "1",
          title: "To Do List",
          description: "Faire une todo List"
        },
        {
          _id: "2",
          title: "Vue",
          description: "Faire du vueJs"
        },
        {
          _id: "3",
          title: "Dance",
          description: "Dance dance dance"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.todo-wrapper {
  display: flex;
  justify-content: center;
  width: 100%;
}

.todo-container {
  width: 400px;
  min-height: 400px;
  background-color: #ededed;
  border-radius: 5px;
}

.todo-item {
  background-color: grey;
  height: 70px;
  margin: 10px;
  color: white;
  border-radius: 5px;
  font-size: 22px;
}

.todo-item-content-header {
  font-weight: bold;
}

.todo-item-content-body {
  margin-top: 0.5rem;
}
</style>
