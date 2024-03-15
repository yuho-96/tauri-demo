<!--
 * @Author: liuyuhao
 * @Date: 2024-03-06 17:21:42
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-15 13:55:02
 * @Description: file description
-->
<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Greet from './components/Greet.vue';
import Page1 from './components/Page1.vue';
import Page2 from './components/Page2.vue';
import Page3 from './components/Page3.vue';
import Login from './components/login.vue';
import Slider from './components/Slider.vue';
import MessageBox from './components/MessageBox.vue';
import { ref } from 'vue';

const showingPage = ref(1);
const isLogin = ref(false);

const toNextPage = () => {
  if (showingPage.value === 3) {
    showingPage.value = 1;
  } else {
    showingPage.value += 1;
  }
};

const onLogin = () => void (isLogin.value = true);
</script>

<template>
  <div class="container">
    <div v-if="isLogin">
      <div class="header">
        设施温室物联网智能测控系统
        <Greet />
      </div>

      <button class="common-btn ml8" @click="() => toNextPage()">通用设置</button>
      <div class="root-top">
        <div class="root-top-item">
          <label for="port">端口号</label>
          <input name="port" disabled type="select" value="8080" />
        </div>
        <div>
          <label for="ip">主机IP</label>
          <input name="ip" disabled type="text" value="10.160.40.200" />
          <button class="ml8" disabled>设置</button>
        </div>
        <div>
          <label for="client">客户端</label>
          <input name="client" disabled type="text" value="--" />
          <button class="ml8" disabled>设置</button>
        </div>
      </div>
      <div class="content mt8">
        <!-- <div> -->
        <Slider />
        <Page1 v-show="showingPage === 1" />
        <Page2 v-show="showingPage === 2" />
        <Page3 v-show="showingPage === 3" />
        <MessageBox />
        <!-- </div> -->
      </div>
    </div>
    <div v-else>
      <Login @login="onLogin" />
    </div>
  </div>
</template>

<style scoped>
.logo.vite:hover {
  filter: drop-shadow(0 0 2em #747bff);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #249b73);
}
.ml8 {
  margin-left: 8px;
}
.mt8 {
  margin-top: 8px;
}
.header {
  margin: 0;
  padding: 0 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: darkblue;
  color: #fff;
  font-size: 22px;
  font-weight: bolder;
}
.common-btn {
  margin: 8px 16px;
  width: fit-content;
}
.root-top {
  box-sizing: border-box;
  padding: 12px 16px;
  margin-top: 8px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid #eee;
  border-bottom: 1px solid #eee;
}
.root-top-item {
  display: flex;
  align-items: center;
}
.content {
  padding: 16px;
  display: flex;
  justify-content: space-between;
}
label {
  margin-right: 8px;
}
input {
  background-color: #eee;
}
</style>
