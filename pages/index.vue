<template>
  <div class="container">
    <div class="text-container">
      <h1 class="main-title">Надежность, качество, удобство. </h1>
      <h2 class="subtitle">Orwork - это безопасный и надежный сайт фриланса, предназначенный для тех, кто заинтересован в качественной работе удаленно.</h2>
      <div class="button-container">
        <button class="svg-button">
          <router-link to="/registration" class="link">
            <span class="button-text">Зарегистрироваться</span>
          </router-link>
        </button>
        <button class="svg-button">
          <router-link to="/projects" class="link">
            <span class="button-text">Найти проект</span>
          </router-link>
        </button>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
definePageMeta({
  layout: 'public'
})
</script>

<style scoped lang="less">
@import "./styles/colors.less";
.container {
  position: relative;
  width: 1000px;
  margin: 0 auto;
  //height: 100vh; /* Высота будет равна высоте видимой области экрана */
}

.text-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center; /* Добавлено выравнивание текста по центру */
}

.main-title {
  font-size: 40px;
  font-weight: bold;
  color: @text-color;
  letter-spacing: 6px;
  margin-top: 300px;
}

.subtitle {
  font-size: 26px;
  text-align: center;
  color: @text-color;
  margin-bottom: 20px;
  letter-spacing: 6px;
  width: 80%;
}

.button-container {
  margin-top: 200px; /* Уменьшено отступ для компактности */
  width: 100%;
  max-width: 900px; /* Использование максимальной ширины */
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.svg-button {
  font-size: 28px;
  width: 380px;
  height: 100px;
  position: relative;
  overflow: hidden;
  transition: filter 0.3s;
  background: @secondary-accent;
  border-radius: 40px;
  border: 1px solid transparent;
}

.link{
  color: @text-color;
  text-decoration: none;
  font-weight: bold;
}
</style>
