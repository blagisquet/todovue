<template>
  <div class="modal" :class="{'is-active': isActive}">
    <div class="modal-content">Insert a thing to do</div>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: {
      required: true,
      type: Boolean
    }
  },
  data: function () {
    return {
      isActive: false
    }
  }
}
</script>

<style scoped lang="scss">

.modal {
  display: none;
  position: fixed;
  z-index: 100;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;

  &.is-active {
    display: block;
  }
}

.modal-content {
  margin: 15% auto;
  padding: 20px;
  border: 4px solid green;
  width: 80%;
  background-color: white;
}
</style>