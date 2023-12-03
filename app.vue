<template>
  <NuxtLayout class="layouts">
    <NuxtPage class="views"/>
  </NuxtLayout>
</template>

<style lang="less">
@import "./styles/fonts.less";
@import "./styles/colors.less";
body {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: @background-color;

}
/* Для WebKit (Chrome, Safari) */
::-webkit-scrollbar {
  width: 12px;
  position: fixed;
  right: 0;
  top: 0;
}

::-webkit-scrollbar-thumb {
  background-color: @text-color;
  border-radius: 6px;
  height: 100px;
}

::-webkit-scrollbar-thumb:hover {
  background-color:@secondary-accent;
}

::-webkit-scrollbar-track {
  background-color: @background-color;
}


/* Общие стили */
body {
  /* Дополнительные стили для вашей страницы */
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
  /*  overflow-x: hidden;
    overflow-y: hidden;*/
}

.views {
  padding-top: 140px;

}


</style>