<!--
 * @Author: liuyuhao
 * @Date: 2024-03-06 17:58:24
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-08 17:57:58
 * @Description: file description
-->
<template>
  <div class="root center-box">
    <div class="tabs">
      <div class="tab" :class="current === 1 && 'current'" @click="() => setCurrent(1)">CPU</div>
      <div class="tab" :class="current === 2 && 'current'" @click="() => setCurrent(2)">
        Service
      </div>
      <div class="tab" :class="current === 3 && 'current'" @click="() => setCurrent(3)">
        消息发送
      </div>
      <div class="tab" :class="current === 4 && 'current'" @click="() => setCurrent(4)">日志</div>
    </div>

    <div class="mt8">
      <div class="mt8 mb8">消息发送:</div>
      <br />
      <input class="mt8 mb8" type="text " />
      <button class="ml8">发送</button>

      <div class="mt8">
        请选择发送对象:
        <input class="mt8" type="checkbox" name="all" />
        <label for="all" class="ml8">对全部客户发送</label>
        <input class="ml8" type="checkbox" name="runtime" />
        <label for="runtime" class="ml8">实时获取数据</label>
        <input class="ml8" type="checkbox" name="min" />
        <label for="min" class="ml8">5min定时清理</label>
      </div>

      <h3>TCP通信内容:</h3>
      <div class="tcp-content">
        时间: {{ +new Date() - 120 }} 接收:[116.147.11.85:56501]70 01 60 16 6F 6E 73 6E 6C 60 66 0D
        3O B2 00 0A O1 0O 63 00 78
        <br />
        时间: {{ +new Date() - 240 }} 接收:[116.147.11.85:56501]70 01 60 16 6F 6E 73 6E 6C 60 66 0D
        3O B2 00 0A O1 0O 63 00 78
        <br />
        时间: {{ +new Date() - 350 }} 接收:[116.147.11.85:56501]70 01 60 16 6F 6E 73 6E 6C 60 66 0D
        3O B2 00 0A O1 0O 63 00 78
        <br />
        时间: {{ +new Date() - 420 }}
        接收:[116.147.11.85:56501]70 01 60 16 6F 6E 73 6E 6C 60 66 0D 3O B2 00 0A O1 0O 63 00 78
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const current = ref(1);

const setCurrent = value => void (current.value = value);
</script>
<style scoped>
.ml8 {
  margin-left: 8px;
}
.tabs {
  display: flex;
  align-items: center;
  gap: 3px;
}
.tab {
  border: 1px solid #7c7c7c;
  padding: 2px 8px;
  border-radius: 8px;
  cursor: pointer;
}
.current {
  background-color: steelblue;
  color: #fff;
}
.tcp-content {
  background-color: #eee;
  padding: 16px;
  color: #000;
  border-radius: 16px;
}
</style>
