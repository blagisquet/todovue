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
      <div class="app-error">
        <div class="form-error">{{formError}}</div>
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
      formError: ""
    };
  },
  computed: {
    isFormValid() {
      return this.form.title.length > 5 && this.form.description.length > 8
        ? true
        : false;
    },
    modal() {
      return this.$refs.modal;
    }
  },
  methods: {
    submitForm() {
      if (this.isFormValid) {
        this.$emit("formSubmitted", { ...this.form });
        this.modal.close();
        // this.close = true;
        // this.$nextTick(() => this.close = false);
        this.resetForm();
      } else {
        if (this.form.title.length <= 5) {
          this.formError = "Title must be 6 characters at least";
        } else if (this.form.description.length <= 8) {
          this.formError = "Description must be 9 characters at least";
        }
      }
    },
    resetForm() {
      this.form.title = "";
      this.form.description = "";
    }
  }
};
</script>

<style scoped lang="scss">
.form-error {
  color: red;
  font-weight: bold;
  margin: 10px 0;
}
</style>