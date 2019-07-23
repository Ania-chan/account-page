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
          placeholder="Password"
          v-model="password"
          :value="password"
          name="password"
          :readonly="(isEdited) ? false : true"
          :maxlength="(isEdited) ? 30 : ''"
          v-validate="'required|min:8|strong'"
          type="password"
          password-reveal
          expanded
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
    <password
      @score="updateScore"
      @feedback="updateFeedback"
      v-model="password"
      :strength-meter-only="true"
      :secure-length="8"
    />
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
      isEdited: false,
      score: 0,
      suggestions: [],
      warning: ""
    };
  },
  // Custom validation rule for password strength
  created() {
    this.$validator.extend("strong", {
      getMessage: () => {
        if (this.warning) {
          return this.warning;
        } else if (this.suggestions.length) {
          return this.suggestions[0];
        }
      },
      validate: () => {
        return this.score >= 2;
      }
    });
  },
  methods: {
    edit() {
      this.isEdited = true;
    },
    updateScore(score) {
      this.score = score;
    },
    updateFeedback({ suggestions, warning }) {
      this.suggestions = suggestions;
      this.warning = warning;
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