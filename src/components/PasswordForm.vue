<template>
  <div class="input-field">
    <b-field label="Password">
      <b-field
        grouped
        group-multiline
        :type="{'is-danger': errors.has('password')}"
        :message="errors.first('password')"
      >
        <b-input
          expanded
          placeholder="Password"
          v-model="password"
          :value="password"
          type="password"
          :maxlength="(isEdited) ? '30' : false"
          password-reveal
          :readonly="(isEdited) ? false : true"
          name="password"
          v-validate="'required|min:8'"
        ></b-input>
        <p class="control">
          <button class="button is-primary" v-show="!isEdited" v-on:click="edit">
            <i class="fas fa-pen"></i>
          </button>
          <button class="button is-success" type="submit" v-show="isEdited" v-on:click="save">
            <i class="fas fa-check"></i>
          </button>
        </p>
      </b-field>
    </b-field>
    <password v-model="password" :strength-meter-only="true" />
  </div>
</template>

<script>
import Password from "vue-password-strength-meter";

export default {
  components: { Password },
  name: "PasswordForm",
  props: ["password"],
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
      this.$validator.validate().then(valid => {
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
.Password {
  padding-left: 0;
  margin-left: 0;
}
</style>