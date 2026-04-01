<template>
  <div class="home-container">
    <!-- 可替换为你的背景图 -->
    <div class="content-bg">
      <div class="text-content">
        <h1>欢迎登录</h1>
        <p>这里是你自定义的文字内容</p>
        <p>可以根据需求自由编辑</p>
        <button @click="handleLogout" class="logout-btn">退出登录</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const handleLogout = () => {
  router.push('/')
}
</script>

<style scoped>
.home-container {
  width: 100vw;
  height: 100vh;
  /* 重点：放在 public 下，直接写 /img/你的图片名 即可 */
  background-image: url("/img/home.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

.content-bg {
  width: 100%;
  height: 100%;
  /* 替换为你的背景图 */
  background-image: url('/assets/home-bg.jpg');
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.text-content {
  text-align: center;
  color: #fff;
  text-shadow: 2px 2px 8px rgba(0,0,0,0.7);
}

h1 {
  font-size: 48px;
  margin-bottom: 20px;
  letter-spacing: 8px;
}

p {
  font-size: 24px;
  margin: 10px 0;
  letter-spacing: 4px;
}

.logout-btn {
  margin-top: 30px;
  padding: 10px 30px;
  font-size: 18px;
  color: #fff;
  background: transparent;
  border: 2px solid #fff;
  border-radius: 4px;
  cursor: pointer;
  transition: all 0.3s;
}

.logout-btn:hover {
  background: #fff;
  color: #333;
}
</style>