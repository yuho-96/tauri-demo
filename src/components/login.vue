<!--
 * @Author: liuyuhao
 * @Date: 2024-03-07 18:02:42
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-07 18:26:44
 * @Description: file description
-->
<template>
  <div class="root">
    <input type="text" class="w-300" placeholder="请输入账号" />
    <input type="text" class="w-300 mb16" placeholder="请输入密码" />
    <button class="w-300 mb16 btn" @click="() => onLogin()">登录</button>
  </div>
</template>

<script setup>
import { defineEmits } from 'vue';

const emits = defineEmits(['login']);

const onLogin = () => void emits('login');
</script>
<style scoped>
.root {
  background: linear-gradient(90deg, #eee, skyblue);
  width: 100%;
  height: 100vh;
  height: 100dvh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .mb16 {
    margin-top: 16px;
  }
  .w-300 {
    width: 300px;
    box-sizing: border-box;
  }
  .btn {
    color: #fff;
    background-color: #4096ff;
    border: none;
  }
}
</style>
