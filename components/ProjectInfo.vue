<!-- ProjectInfo.vue -->
<template>
  <div class="project-info card">
    <h3 class="card-title">{{ projectName }}</h3>
    <p class="card-text"><strong>Срок приема откликов:</strong> {{ deadline }}</p>
    <p class="card-text"><strong>Срок проекта:</strong> {{ projectDuration }}</p>
    <p class="card-text"><strong>Бюджет проекта:</strong> {{ projectBudget }}</p>
  </div>
</template>

<script>
export default {
  props: {
    projectName: String,
    deadline: String,
    projectDuration: String,
    projectBudget: String,
  },
};
</script>

<style scoped lang="less">
@import "./styles/colors.less";
.project-info {
  border: 1px solid @text-color;
  border-radius: 16px;
  padding: 15px;
  margin: 15px 0;
  color: @text-color;
}

.card-title {
  font-size: 26px;
  margin-bottom: 10px;
}

.card-text {
  margin-bottom: 5px;
  font-size: 20px;
}


</style>
