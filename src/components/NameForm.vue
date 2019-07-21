<template>
  <b-field grouped>
    <b-input expanded v-model="name" :value="name" :readonly="(isEdited) ? trfalseue : true"></b-input>
    <b-input expanded v-model="surname" :value="surname" :readonly="(isEdited) ? false : true"></b-input>
    <p class="control">
      <button class="button is-primary" v-show="!isEdited" v-on:click="edit">
        <i class="fas fa-pen"></i>
      </button>
      <button class="button is-success" v-show="isEdited" v-on:click="save">
        <i class="fas fa-check"></i>
      </button>
    </p>
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
      this.isEdited = false;
    }
  }
};
</script>

<style scoped>
</style>
