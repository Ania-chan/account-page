<template>
  <form @submit.prevent="validateBeforeSubmit">
    <b-field
      grouped
      :type="{'is-danger': errors.has('password')}"
      :message="errors.first('password')"
    >
      <b-input
        expanded
        placeholder="Password"
        v-model="password"
        :value="password"
        type="password"
        :maxlength="(isEdited) ? '30' : false"
        password-reveal
        :readonly="(isEdited) ? false : true"
        name="password"
        v-validate="'required|min:8'"
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
  name: "PasswordForm",
  props: ["password"],
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