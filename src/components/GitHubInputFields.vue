<template>
  <form class="input-fields">
    <b-field class="input-field" label="Token">
      <b-input placeholder="Token" v-model="token" :value="token" name="token" type="text" expanded></b-input>
    </b-field>
    <b-field class="input-field" label="Repository Name">
      <b-input
        placeholder="username/repository"
        v-model="name"
        :value="name"
        name="name"
        type="text"
        expanded
      ></b-input>
    </b-field>
    <b-field class="input-field" label="Title">
      <b-input placeholder="Title" v-model="title" :value="title" name="title" type="text" expanded></b-input>
    </b-field>
    <b-field class="input-field" label="Issue">
      <b-input placeholder="Issue" v-model="issue" :value="issue" name="issue" type="text" expanded></b-input>
    </b-field>
    <button type="submit" v-on:click="submitIssue">Submit</button>
  </form>
</template>

<script>
import axios from "axios";

export default {
  name: "GitHubInputFields",
  data() {
    return {
      token: "",
      name: "",
      title: "",
      issue: ""
    };
  },
  // Update the user object after editing it in the form
  methods: {
    submitIssue: function(event) {
      event.preventDefault();
      const data = {
        title: this.title,
        body: this.issue
      };

      let axiosConfig = {
        headers: { Authorization: `token ${this.token}` }
      };
      axios
        .post(
          `https://api.github.com/repos/${this.name}/issues`,
          data,
          axiosConfig
        )
        .then(res => {
          console.log("RESPONSE RECEIVED: ", res);
        })
        .catch(err => {
          console.log("AXIOS ERROR: ", err);
        });
    }
  }
};
</script>

<style scoped>
.input-fields {
  width: 100%;
}

.input-field {
  margin: 20px 0;
}

p.help.is-danger {
  margin-top: 0;
}
</style>