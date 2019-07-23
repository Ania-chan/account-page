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
  }
};
</script>

<style scoped>
.avatar {
  margin-top: 25px;
}

.card {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
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
  padding: 10px 10px;
  width: 100%;
}

@media (min-width: 1024px) {
  .card {
    width: 50%;
  }
  .card-content {
    padding: 10px 50px;
    width: 100%;
  }
}
</style>
