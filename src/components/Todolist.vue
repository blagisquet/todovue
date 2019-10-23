<template>
  <div class="todo-list">
    <Todoitem v-for="todo in todos" 
    :key="todo._id"
    :title="todo.title"
    :description="todo['description']" />
  </div>
</template>

<script>
import Todoitem from '@/components/Todoitem'
export default {
  name:'Todolist',
  components: {
    Todoitem,
  },
  props: {
    todos: {
      required: true,
      type: Array
    }
  }
}
</script>