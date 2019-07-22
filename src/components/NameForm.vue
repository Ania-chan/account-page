<template>
  <b-field class="input-field" label="Full Name">
    <b-field
      grouped
      group-multiline
      :type="{'is-danger': errors.has('name')}"
      :message="errors.first('name')"
    >
      <b-input
        expanded
        placeholder="Name"
        v-model="name"
        :value="name"
        name="name"
        :readonly="(isEdited) ? false : true"
        v-validate="'required|max:30'"
      ></b-input>
      <b-field
        grouped
        group-multiline
        :type="{'is-danger': errors.has('surname')}"
        :message="errors.first('surname')"
      >
        <b-input
          expanded
          placeholder="Surname"
          v-model="surname"
          :value="surname"
          name="surname"
          :readonly="(isEdited) ? false : true"
          v-validate="'required|max:30'"
        ></b-input>
      </b-field>
      <p class="control">
        <button class="button is-primary" v-show="!isEdited" v-on:click="edit">
          <i class="fas fa-pen"></i>
        </button>
        <button class="button is-success" v-show="isEdited" type="submit" v-on:click="save">
          <i class="fas fa-check"></i>
        </button>
      </p>
    </b-field>
  </b-field>
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
      this.$validator.validateAll().then(valid => {
        if (!valid) {
          this.$toast.open({
            message: "Form is not valid! Please check the fields.",
            type: "is-danger",
            position: "is-bottom"
          });
        } else {
          this.isEdited = false;
          this.$emit("update-password", this.password);
        }
      });
    }
  }
};
</script>

<style scoped>
</style>
