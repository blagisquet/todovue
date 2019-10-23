<template>
  <div class="todo-item">
    <div class="todo-item-content">
      <div class="todo-item-content-header">{{title}}</div>
      <div class="todo-item-content-body">{{description}}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "description"]
};
</script>