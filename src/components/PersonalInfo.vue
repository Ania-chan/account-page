<template>
  <section>
    <b-field label="Full Name">
      <b-input value="Han Solo" icon-pack="fas" icon="pen" readonly></b-input>
    </b-field>
    <b-field label="Email">
      <b-input type="email" icon-pack="fas" icon="pen" value="millenium.falcon@gmail.com" readonly></b-input>
    </b-field>
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
    </b-field>
  </section>
</template>

<script>
export default {
  name: "PersonalInfo"
};
</script>

<style scoped>
</style>
