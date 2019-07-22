<template>
  <div class="card">
    <div class="card-header">
      <div class="card-header-title">My Account</div>
    </div>
    <figure class="avatar image">
      <v-gravatar :email="user.email" alt="Profile picture" :size="80" default-img="identicon" />
    </figure>
    <div class="card-content">
      <PersonalInfo v-bind:user="user" />
    </div>
  </div>
</template>

<script>
import PersonalInfo from "./PersonalInfo";

export default {
  name: "AccountCard",
  components: {
    PersonalInfo
  },
  data() {
    return {
      user: {
        name: "Han",
        surname: "Solo",
        email: "millenium.falcon@gmail.com",
        password: "Ch3wb4cc4"
      }
    };
  },
  computed: {}
};
</script>

<style scoped>
.avatar {
  margin-top: 30px;
}

.card {
  width: 55%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-bottom: 30px;
}

.card-header {
  width: 100%;
}

.card-header-title {
  display: flex;
  justify-content: center;
  font-family: "Lobster", cursive;
  font-size: 2em;
  color: #ff5f6d;
}

.card-content {
  padding: 10px 50px;
  width: 100%;
}
</style>
