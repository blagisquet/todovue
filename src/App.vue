<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <Todolist :todos="todos" />
        <TodoCreate @formSubmitted="createTodo" />
      </div>
    </div>
  </div>
</template>

<script>
import Todolist from "@/components/Todolist";
import TodoCreate from "@/components/TodoCreate";

export default {
  name: "app",
  components: {
    Todolist,
    TodoCreate
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
  },
  methods: {
    createTodo(todo) {
      this.todos.push(todo);
    }
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

.todo-button {
  font-size: 20px;
  padding: 10px;
  border-radius: 4px;
  background-color: purple;
  color: white;
  margin: 12px 10px 10px;
  cursor: pointer;
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
  height: 120px;
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

.app-form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 60%;

  label {
    display: block;
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 5px;
  }

  input {
    padding: 10px;
    font-size: 18px;
    width: 50%;
  }

  .form-control {
    margin-bottom: 10px;
  }

  .button {
    background-color: purple;
    color: white;
    padding: 10px;
    border-radius: 5px;
    font-size: 18px;
    cursor: pointer;
    margin-top: 10px;
  }
}
</style>
