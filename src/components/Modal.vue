<template>
  <div>
    <div class="todo-button">
      <div @click="isOpen = true" class="button">New todo</div>
    </div>
    <div class="modal" :class="{'is-active': isOpen}">
      <div class="modal-content">
        <span @click="close" class="close">&times;</span>
        <slot />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // props: {
  //   close: {
  //     type: Boolean,
  //     required: false,
  //   }
  // },
  data() {
    return {
      isOpen: false,
    }
  },
  watch: {
    close(isClose) {
      if (isClose === true && this.isOpen === true) {
        this.isOpen = false;
      }
    }
  },
  methods: {
    close() {
      this.isOpen = false
    }
  }
}
</script>

<style lang="scss">

.close {
  color: grey;
  float: right;
  font-size: 24px;
  font-weight: bold;
  cursor: pointer;
}

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