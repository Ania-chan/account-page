<template>
  <div class="card">
    <div class="card-header">
      <div class="card-header-title">My Account</div>
    </div>
    <figure class="avatar image is-80x80">
      <img src="https://www.gravatar.com/avatar/HASH?s=80&d=identicon" alt="Profile picture" />
    </figure>
    <div class="card-content">
      <p>
        Full name:
        <span>Han Solo</span>
      </p>
      <p>
        Email address:
        <span>millenium.falcon@gmail.com</span>
      </p>
      <p>
        Password:
        <span>************</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "AccountCard"
};
</script>

<style scoped>
.avatar {
  width: 80px;
  height: 80px;
  margin: 20px;
}
</style>
