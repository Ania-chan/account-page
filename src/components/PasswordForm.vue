<template>
  <b-field label="Password">
    <b-input
      value="Chewbacca"
      icon-pack="fas"
      icon="pen"
      type="password"
      maxlength="30"
      readonly
      password-reveal
    ></b-input>
    <p class="control">
      <button class="button is-primary">
        <i class="fas fa-pen"></i>
      </button>
    </p>
  </b-field>
</template>

<script>
export default {
  name: "PasswordForm"
};
</script>

<style scoped>
</style>