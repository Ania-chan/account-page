<template>
  <div class="card">
    <div class="card-header">
      <div class="card-header-title">My Account</div>
    </div>
    <figure class="avatar image">
      <img :src="url" alt="Profile picture" />
    </figure>
    <div class="card-content">
      <PersonalInfo />
    </div>
  </div>
</template>

<script>
import PersonalInfo from "./PersonalInfo";
import gravatar from "gravatar";

export default {
  name: "AccountCard",
  components: {
    PersonalInfo
  },
  data() {
    return {
      url: gravatar.url("millenium.falcon@gmail.com", {
        s: "80",
        r: "pg",
        d: "identicon"
      })
    };
  }
};
</script>

<style scoped>
.avatar {
  margin-top: 30px;
}

.card {
  width: 40%;
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
}

.card-content {
  padding: 10px 50px;
  width: 100%;
}
</style>
