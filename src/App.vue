<template>
  <div id="app">
    <section class="section main-page">
      <div class="container">
        <AccountCard />
      </div>
    </section>
  </div>
</template>

<script>
import AccountCard from "./components/AccountCard";
import Vue from "vue";
import Buefy from "buefy";
import "buefy/dist/buefy.css";

Vue.use(Buefy);
export default {
  name: "app",
  components: {
    AccountCard
  }
};
</script>

<style>
#app {
  font-family: "Open Sans", sans-serif;
}

.main-page {
  height: 100vh;
}

.container {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
