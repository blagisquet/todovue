<template>
  <div class="todo-item">
    <div class="todo-item-content">
      <div class="todo-item-content-header">{{title}}</div>
      <div class="todo-item-content-body">{{description}}</div>
      <button class="edit">Edit</button>
      <button class="delete">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "description"]
};
</script>

<style scoped lang="scss">
.edit {
  margin-top: 10px;
  padding: 10px;
  background-color: orange;
  border-radius: 5px;
}

.delete {
  border-radius: 5px;
  margin-top: 10px;
  margin-left: 5px;
  padding: 10px;
  background: red;
}
</style>