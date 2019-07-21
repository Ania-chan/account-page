<template>
  <form @submit.prevent="validateBeforeSubmit">
    <b-field grouped :type="{'is-danger': errors.has('name')}" :message="errors.first('name')">
      <b-input
        expanded
        placeholder="Name"
        v-model="name"
        :value="name"
        name="name"
        :readonly="(isEdited) ? false : true"
        v-validate="'required|max:30'"
      ></b-input>
      <b-input
        expanded
        placeholder="Surname"
        v-model="surname"
        :value="surname"
        name="surname"
        :readonly="(isEdited) ? false : true"
        v-validate="'required|max:30'"
      ></b-input>

      <p class="control">
        <button class="button is-primary" v-show="!isEdited" v-on:click="edit">
          <i class="fas fa-pen"></i>
        </button>
        <button class="button is-success" v-show="isEdited" type="submit" v-on:click="save">
          <i class="fas fa-check"></i>
        </button>
      </p>
    </b-field>
  </form>
</template>

<script>
export default {
  name: "NameForm",
  props: ["name", "surname"],
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
