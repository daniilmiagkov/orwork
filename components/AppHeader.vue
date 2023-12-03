<template>
  <div class="header">
    <section class="links">
      <NuxtLink to="/" class="header-link">
        <img class="header-img logo-image" :src="logo" />
      </NuxtLink>
      <NuxtLink to="/contacts" class="header-link">
        <div class="header-text">Контакты</div>
      </NuxtLink>
      <NuxtLink to="/projects" class="header-link">
        <div class="header-text">Проекты</div>
      </NuxtLink>
      <NuxtLink to="/about" class="header-link">
        <div class="header-text">О нас</div>
      </NuxtLink>
      <NuxtLink to="/login" class="header-link">
        <div class="header-text">Вход</div>
      </NuxtLink>
    </section>
<!--
    <img class="header-img account-image" :src="account"/>
--><router-link to="/login" class="header-link">
    <img class="header-img find-image" :src="find" />  </router-link>
  </div>
</template>

<script setup>
  import { ref } from 'vue'
  import account from '../assets/68c422509ce8653bfb5335ee2b2a9443.png'
  import logo from '../assets/Group 1 (1).png'
  import find from '../assets/40ffc4689710d2e3ab48090436be4ce0.png'

</script>

<style lang="less">
@import "./styles/colors.less";
.header {
  background-color: @background-color;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000; /* Установите z-index, если вам нужно контролировать слои */

}

.header-img {
  display: block;
}

.header-link {
  text-align: center;
  color: @text-color;
  font-size: 20px;
  font-weight: 400;
  text-decoration: none;
  text-transform: uppercase;
  font-style: normal;
}

.links {
  display: flex;
  justify-content: space-around;
  width: 70%;
  align-items: center;

}

/* Стили для изображения с аккаунтом */
.find-image {
  margin-right: 30px;
  width: 30px;
  height: 30px;
}

.logo-image {
  height: 50px;
  width: 180px;
  background-color: @text-color;
}
</style>
