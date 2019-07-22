<template>
  <form @submit.prevent="validateBeforeSubmit">
    <label class="label">Email</label>
    <b-field
      grouped
      group-multiline
      :type="{'is-danger': errors.has('email')}"
      :message="errors.first('email')"
    >
      <b-input
        expanded
        placeholder="Email"
        v-model="email"
        :value="email"
        :readonly="(isEdited) ? false : true"
        v-validate="'required|email'"
        name="email"
        type="text"
      ></b-input>
      <p class="control">
        <button class="button is-primary" v-show="!isEdited" v-on:click="edit">
          <i class="fas fa-pen"></i>
        </button>
        <button class="button is-success" type="submit" v-show="isEdited" v-on:click="save">
          <i class="fas fa-check"></i>
        </button>
      </p>
    </b-field>
  </form>
</template>

<script>
export default {
  name: "EmailForm",
  props: ["email"],
  data() {
    return {
      isEdited: false
    };
  },
  methods: {
    edit() {
      this.isEdited = true;
    },
    save() {
      this.isEdited = false;
      this.$emit("update-email", this.email);
    },
    validateBeforeSubmit() {
      this.$validator.validateAll().then(result => {
        if (result) {
          this.$toast.open({
            message: "Form is valid!",
            type: "is-success",
            position: "is-bottom"
          });
          return;
        }
        this.$toast.open({
          message: "Form is not valid! Please check the fields.",
          type: "is-danger",
          position: "is-bottom"
        });
      });
    }
  }
};
</script>

<style scoped>
</style>