<template>
  <div class="card">
    <div class="card-header">
      <div class="card-header-title">GitHub Issue Creator</div>
    </div>
    <div class="card-content">
      <GitHubInputFields />
    </div>
  </div>
</template>

<script>
import GitHubInputFields from "./GitHubInputFields";

export default {
  name: "GitHubIssueCard",
  components: {
    GitHubInputFields
  },
  data() {
    return {};
  }
};
</script>

<style scoped>
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

@media (min-width: 768px) {
  .card {
    width: 50%;
  }
  .card-content {
    padding: 10px 50px;
  }
}
</style>
