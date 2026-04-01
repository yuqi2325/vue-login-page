<template>
  <!-- 路由视图：登录页 / 首页 都会在这里显示 -->
  <div id="app">
    <router-view />
  </div>
</template>

<script setup>
// 无需写任何代码
</script>

<style>
/* 全局样式重置，让页面铺满屏幕、无留白 */  
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>