<template>
  <b-field label="Email">
    <b-input type="email" icon-pack="fas" icon="pen" value="millenium.falcon@gmail.com" readonly></b-input>
    <p class="control">
      <button class="button is-primary">
        <i class="fas fa-pen"></i>
      </button>
    </p>
  </b-field>
</template>

<script>
export default {
  name: "EmailForm",
  props: ["email"]
};
</script>

<style scoped>
</style>