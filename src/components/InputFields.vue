<template>
  <div class="input-fields">
    <NameForm
      v-bind:name="user.name"
      v-bind:surname="user.surname"
      v-on:update-name="nameUpdateHandler"
      v-on:update-surname="surnameUpdateHandler"
    />
    <EmailForm v-on:update-email="emailUpdateHandler" v-bind:email="user.email" />
    <PasswordForm v-on:update-password="passwordUpdateHandler" v-bind:password="user.password" />
  </div>
</template>

<script>
import NameForm from "./NameForm";
import EmailForm from "./EmailForm";
import PasswordForm from "./PasswordForm";

export default {
  name: "InputFields",
  props: ["user"],
  components: {
    NameForm,
    EmailForm,
    PasswordForm
  },
  // Update the user object after editing it in the form
  methods: {
    nameUpdateHandler: function(name) {
      this.user.name = name;
    },
    surnameUpdateHandler: function(surname) {
      this.user.surname = surname;
    },
    emailUpdateHandler: function(email) {
      this.user.email = email;
    },
    passwordUpdateHandler: function(password) {
      this.user.password = password;
    }
  }
};
</script>

<style scoped>
.input-fields {
  width: 100%;
}

.input-field {
  margin: 20px 0;
}

p.help.is-danger {
  margin-top: 0;
}
</style>