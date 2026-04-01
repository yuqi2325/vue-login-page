<template>
  <div class="login-container">
    <div class="login-box">
      <div class="input-group">
        <label class="input-label">USERNAME</label>
        <input
          v-model="username"
          type="text"
          class="input-field"
          placeholder=""
        />
      </div>
      <div class="input-group">
        <label class="input-label">PASSWORD</label>
        <input
          v-model="password"
          type="password"
          class="input-field"
          placeholder=""
        />
      </div>
      <button @click="handleLogin" class="login-btn">LOGIN</button>
      <p v-if="errorMsg" class="error-msg">{{ errorMsg }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
const username = ref('')
const password = ref('')
const errorMsg = ref('')

// 前端写死的账号密码
const VALID_USER = 'admin'
const VALID_PWD = '123456'

const handleLogin = () => {
  errorMsg.value = ''
  if (username.value === VALID_USER && password.value === VALID_PWD) {
    // 登录成功，跳转到首页
    router.push('/home')
  } else {
    alert("鸡蛋灌饼提示您:'用户名或密码错误,在回去看看书吧,小笨蛋'")
  }
}
</script>

<style scoped>
.login-container {
  width: 100vw;
  height: 100vh;
  /* 重点：放在 public 下，直接写 /img/你的图片名 即可 */
  background-image: url("/img/login.jpg");
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
.login-box {
  width: 500px;
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.input-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.input-label {
  font-family: 'Arial Black', sans-serif;
  font-size: 28px;
  letter-spacing: 6px;
  color: #fff;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.input-field {
  width: 100%;
  height: 50px;
  background: #fff;
  border: none;
  outline: none;
  padding: 0 15px;
  font-size: 18px;
  border-radius: 2px;
  box-shadow: 3px 3px 6px rgba(0,0,0,0.2);
}

.login-btn {
  margin-top: 20px;
  align-self: center;
  padding: 12px 40px;
  font-family: 'Arial Black', sans-serif;
  font-size: 20px;
  letter-spacing: 4px;
  color: #fff;
  background: transparent;
  border: 2px solid #fff;
  border-radius: 4px;
  cursor: pointer;
  transition: all 0.3s;
}

.login-btn:hover {
  background: #fff;
  color: #8B3A3A;
}

.error-msg {
  color: #ff4444;
  font-size: 14px;
  text-align: center;
  margin: 0;
}
</style>