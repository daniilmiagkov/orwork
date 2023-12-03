<template>
  <button class="svg-button" >
    <router-link :to="path">
      <span class="button-text">{{ buttonText }}</span>
    </router-link>
  </button>
</template>

<script>
export default {
  props: {
    buttonText: {
      type: String,
      default: "Кнопка",
    },
    path: {
      type: String,
      default: "/",
    },
  },
};
</script>

<style scoped lang="less">
@import "@/styles/colors.less";



.cta-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0);
  transition: background 0.3s;
  z-index: 1;
}


.button-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 16px;
  text-transform: uppercase;
  font-weight: 300;
  text-align: center;
  color: @text-color;
  z-index: 2;
}
</style>
