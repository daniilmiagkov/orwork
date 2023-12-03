<!-- ProjectsList.vue -->
<template>
  <div class="container">
    <div class="controls">
      <button @click="toggleView" class="button">Список</button>
      <button @click="sortByName" class="button">Сортировка по названию</button>
      <button @click="sortByDeadline" class="button">Сортировка по сроку</button>
      <button @click="sortByBudget" class="button">Сортировка по бюджету</button>
      <button @click="filterByBudget(150000)" class="button">Фильтр по бюджету (>150000)</button>
    </div>
    <div :class="{ 'project-list': isListView, 'project-grid': !isListView }">

        <ProjectInfo v-for="(project, index) in filteredProjects" :key="index"
            :projectName="project.name"
            :deadline="project.deadline"
            :projectDuration="project.duration"
            :projectBudget="project.budget"
        />
    </div>
  </div>
</template>

<script>
import ProjectInfo from "../components/ProjectInfo.vue";

export default {
  components: {
    ProjectInfo,
  },
  data() {
    return {
      projects: [
        {
          name: "Инновационный стартап",
          deadline: "15.06.2024",
          duration: "4 месяца",
          budget: "250000",
        },
        {
          name: "Разработка мобильного приложения",
          deadline: "01.08.2024",
          duration: "3 месяца",
          budget: "180000",
        },
        {
          name: "Оптимизация веб-платформы",
          deadline: "10.07.2024",
          duration: "2.5 месяца",
          budget: "200000",
        },
        {
          name: "Исследовательский проект в области искусственного интеллекта",
          deadline: "20.09.2024",
          duration: "6 месяцев",
          budget: "300000",
        },
        {
          name: "Проектирование умного города",
          deadline: "05.10.2024",
          duration: "4 месяца",
          budget: "220000",
        },
        {
          name: "Обучение нейронной сети для медицинского анализа",
          deadline: "15.11.2024",
          duration: "3 месяца",
          budget: "190000",
        },
        {
          name: "Реализация блокчейн-технологий в финансовой сфере",
          deadline: "01.12.2024",
          duration: "5 месяцев",
          budget: "280000",
        },
        {
          name: "Создание платформы для онлайн-образования",
          deadline: "10.02.2025",
          duration: "4 месяца",
          budget: "230000",
        },
        {
          name: "Разработка системы для автоматизации производства",
          deadline: "20.03.2025",
          duration: "3.5 месяца",
          budget: "210000",
        },
        {
          name: "Исследование новых материалов в промышленности",
          deadline: "01.05.2025",
          duration: "6 месяцев",
          budget: "320000",
        },

      ],
      isListView: true,
      filteredProjects: [],
    };
  },
  methods: {
    toggleView() {
      this.isListView = !this.isListView;
    },
    sortByName() {
      this.filteredProjects = [...this.projects].sort((a, b) => a.name.localeCompare(b.name));
    },
    sortByDeadline() {
      this.filteredProjects = [...this.projects].sort((a, b) => new Date(a.deadline) - new Date(b.deadline));
    },
    sortByBudget() {
      this.filteredProjects = [...this.projects].sort((a, b) => parseInt(a.budget) - parseInt(b.budget));
    },
    filterByBudget(minBudget) {
      this.filteredProjects = this.projects.filter(project => parseInt(project.budget) > minBudget);
    },
  },
  mounted() {
    this.filteredProjects = Object.assign([], this.projects);
  },
};
</script>

<style scoped lang="less">
@import "./styles/colors.less";

.container {
  width: 90%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;

}

.title {
  font-size: 30px;
  text-align: center;
  color: @text-color;
}

.view-toggle {
  margin-bottom: 10px;
}

.controls {
  display: flex;
  justify-content: space-between; /* Изменено расположение кнопок */
  margin-bottom: 10px;
}

.button {
  font-size: 20px;
  padding: 10px;
  background-color: @text-color;
  color: @background-color;
  border: 1px solid;
  border-radius: 16px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.button:hover {
  background-color: @secondary-accent; /* Замените на цвет по вашему выбору */
  //color: @text-color;
}

.project-list {
  display: grid;
  grid-template-columns: repeat(1fr);
}

.project-list .project-info {
  min-height: 200px;
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
  margin: 0 auto;
  width: 100%;
}

.project-grid .project-info {
  min-height: 320px;
}
</style>
