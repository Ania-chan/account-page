<template>
  <div id="app">
    <section class="section main-page">
      <div class="container">
        <AccountCard />
        <GitHubIssueCard />
      </div>
    </section>
  </div>
</template>

<script>
import AccountCard from "./components/AccountCard";
import Vue from "vue";
import Buefy from "buefy";
import "buefy/dist/buefy.css";
import VeeValidate from "vee-validate";
import Gravatar from "vue-gravatar";
import GitHubIssueCard from "./components/GitHubIssueCard";

Vue.component("v-gravatar", Gravatar);

Vue.use(VeeValidate, {
  events: ""
});
Vue.use(Buefy);

export default {
  name: "app",
  components: {
    AccountCard,
    GitHubIssueCard
  }
};
</script>

<style>
#app {
  font-family: "Open Sans", sans-serif;
}

.main-page {
  height: 100vh;
  background: #ff5f6d; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to left,
    #ffc371,
    #ff5f6d
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to left,
    #ffc371,
    #ff5f6d
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.container {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
