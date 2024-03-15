<!--
 * @Author: liuyuhao
 * @Date: 2024-03-08 16:14:25
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-08 17:02:40
 * @Description: file description
-->
<template>
  <div class="root">
    <button>消息接收</button>
    <div class="message-area mt8 shadow-border">
      <div v-for="(msg, index) in messageQueue" :key="msg.id">
        {{ msg.content }}
      </div>
    </div>
    <div class="btns mt8">
      <button class="btn" @click="pushMessageQueue">显示</button>
      <button class="ml48 btn" @click="clearMessageQueue">清空</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import dayjs from 'dayjs';

const messageQueue = ref([]);
const actions = ['服务器连接中', '服务器连接成功', '主题订阅成功', '连接异常', '服务器断开'];

const pushMessageQueue = () => {
  messageQueue.value.push({
    content: `${dayjs(new Date()).format('YYYY-MM-DD HH:mm:ss')} ${
      actions[Math.floor(Math.random() * 100) % 5]
    }`,
    id: messageQueue.value.length + 1,
  });
};

const clearMessageQueue = () => void (messageQueue.value = []);
</script>
<style scoped>
.root {
  width: 25%;
  display: flex;
  flex-direction: column;
}
.message-area {
  min-height: 600px;
  border: 1px solid #eee;
  border-radius: 8px;
  background-color: #fff;
  padding: 16px;
}
.ml48 {
  margin-left: 48px;
}
.mt8 {
  margin-top: 8px;
}
.btns {
  text-align: center;
  border-radius: 8px;
  background-color: #fff;
  padding: 16px;
}
.btn {
  border-radius: 8px;
  background: steelblue;
  color: #eee;
}
</style>
