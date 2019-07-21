<template>
  <b-field label="Full Name">
    <b-input v-model="name" value="Han Solo" readonly></b-input>
    <p class="control">
      <button class="button is-primary">
        <i class="fas fa-pen"></i>
      </button>
    </p>
  </b-field>
</template>

<script>
export default {
  name: "NameForm",
  props: ["name", "surname"]
};
</script>

<style scoped>
</style>
