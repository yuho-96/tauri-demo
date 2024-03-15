<!--
 * @Author: liuyuhao
 * @Date: 2024-03-06 17:21:42
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-06 17:51:24
 * @Description: file description
-->
<script setup lang="ts">
import { ref } from 'vue';
import { invoke } from '@tauri-apps/api/tauri';

const greetMsg = ref('');
const name = ref('');

async function greet() {
  // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
  greetMsg.value = await invoke('greet', { name: name.value });
}
</script>

<template>
  <form class="row" @submit.prevent="greet">
    <input id="greet-input" v-model="name" placeholder="请输入要搜索的设备名称或型号" />
    <button type="submit">搜索</button>
  </form>
</template>

<style>
.row {
  display: inline-flex;
  justify-content: flex-end;
  font-size: 16px;
  margin: 16px;
}
</style>
