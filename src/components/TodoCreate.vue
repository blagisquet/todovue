<template>
  <Modal ref="modal">
    <form class="app-form">
      <div class="form-control">
        <label class="label">Title</label>
        <input v-model="form.title" type="text" />
      </div>
      <div class="form-control">
        <label class="label">Description</label>
        <input v-model="form.description" type="text" />
      </div>
      <div @click="submitForm" class="button" type="button">Add todo</div>
    </form>
  </Modal>
</template>

<script>
import Modal from "@/components/Modal";
export default {
  components: {
    Modal
  },
  data() {
    return {
      form: {
        title: "",
        description: ""
      },
      close: false
    }
  },
  computed: {
    isFormValid() {
      return this.form.title.length > 5 && this.form.description.length > 8 ? true : false
    },
    modal() {
      return this.$refs.modal;
    }
  },
  methods: {
    submitForm() {
      if (this.isFormValid) {
      this.$emit('formSubmitted', {...this.form});
      this.modal.close()
      // this.close = true;
      // this.$nextTick(() => this.close = false);
      this.resetForm();
      }
    },
    resetForm() {
      this.form.title = '';
      this.form.description = '';
    }
  }
};
</script>

<style scoped lang="scss">

</style>