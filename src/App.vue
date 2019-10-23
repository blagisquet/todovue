<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <Todolist :todos="todos" />
        <div class="todo-button">
          <div @click="openModal" class="button">New todo</div>
        </div>
      </div>
    </div>
    <Modal :isOpen="isModalOpen" />
  </div>
</template>

<script>
import Todolist from "@/components/Todolist";
import Modal from "@/components/Modal";

export default {
  name: "app",
  components: {
    Todolist,
    Modal,
  },
  data() {
    return {
      isModalOpen: false,
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
    openModal() {
      this.isModalOpen = !this.isModalOpen
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
  margin: 120px 10px 10px;
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
