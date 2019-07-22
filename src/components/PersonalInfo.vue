<template>
  <div class="personal-info">
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
  name: "PersonalInfo",
  props: ["user"],
  components: {
    NameForm,
    EmailForm,
    PasswordForm
  },
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
.personal-info {
  width: 100%;
}
.input-field {
  margin: 20px 0;
}
</style>