<template>
  <section>
    <NameForm v-bind:name="user.name" v-bind:surname="user.surname" />
    <EmailForm v-bind:email="user.email" />
    <PasswordForm v-bind:password="user.password" />
  </section>
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
  }
};
</script>

<style scoped>
</style>