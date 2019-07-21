<template>
  <section>
    <NameForm />
    <EmailForm />
    <PasswordForm />>
  </section>
</template>

<script>
import NameForm from "./NameForm";
import EmailForm from "./EmailForm";
import PasswordForm from "./PasswordForm";

export default {
  name: "PersonalInfo",
  components: {
    NameForm,
    EmailForm,
    PasswordForm
  }
};
</script>

<style scoped>
</style>