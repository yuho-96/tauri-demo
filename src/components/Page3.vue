<!--
 * @Author: liuyuhao
 * @Date: 2024-03-06 18:04:30
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-15 13:37:43
 * @Description: file description
-->
<template>
  <div class="root center-box">
    <div class="title">远程控制</div>
    <table class="mb8" align="center">
      <thead>
        <tr>
          <th scope="col">index</th>
          <th scope="col" class="w-300">directiveName</th>
          <th scope="col" class="w-300">HexNum</th>
        </tr>
      </thead>
      <tbody align="center">
        <tr>
          <th scope="row">1</th>
          <th scope="row">风机开启</th>
          <td>0xe2</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <th scope="row">风机关闭</th>
          <td>0xe3</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <th scope="row">喷淋装置开启</th>
          <td>0xe4</td>
        </tr>
        <tr>
          <th scope="row">4</th>
          <th scope="row">喷淋装置关闭</th>
          <td>0xe5</td>
        </tr>
        <tr>
          <th scope="row">5</th>
          <th scope="row">-</th>
          <td>{{ '-' }}</td>
        </tr>
        <tr>
          <th scope="row">6</th>
          <th scope="row">-</th>
          <td>-</td>
        </tr>
      </tbody>
    </table>
    <div class="bt8 mb8 func">
      <div class="mb8">列表相关操作:</div>
      <div class="func-content">
        <button class="ml8">修改</button>
        <button class="ml8">删除</button>
        <button class="ml8">刷新</button>
      </div>
    </div>
    <div class="bt8 mb8 func">
      <div class="mb8">添加指令</div>
      <div class="func-content">
        <span>
          十六进制指令:
          <input style="width: 100px" type="text" />
        </span>
        <span>
          指令释义:
          <input style="width: 100px" type="text" />
        </span>
        <button>提交</button>
      </div>
    </div>
    <div class="wrapper">
      <div class="bt8 mb8 half-func">
        <div class="mb8">指令选择发送框</div>
        <div class="func-content">
          <select value="1">
            <option value="1">风机开启</option>
          </select>
          <div class="btns">
            <button>添加</button>
            <button>删除</button>
          </div>
          <textarea style="display: block; width: 100%" :rows="7" />
        </div>
      </div>
      <div class="mb8 half-func">
        <div class="mb8">DTU选择发送框</div>

        <div class="func-content">
          <select value="1">
            <option value="1">selectvalue001</option>
          </select>
          <div class="btns">
            <button>添加</button>
            <button>删除</button>
          </div>
          <textarea style="display: block; width: 100%" :rows="7" />
        </div>
      </div>
    </div>

    <button class="footer-btn">发送</button>
  </div>
</template>

<script setup>
import { onBeforeMount, onMounted } from 'vue';
console.log('1-setup');
onBeforeMount(() => {
  console.log('2-api request----onBeforeMount');
});
onMounted(() => {
  console.log('3-dom operation-------onMounted');
});
</script>
<style scoped>
.title {
  width: 100%;
  font-size: 20px;
  padding: 12px;
  font-weight: bold;
  border-radius: 16px;
  color: steelblue;
}
table {
  border-collapse: collapse;
  border: 2px solid rgb(140 140 140);
  font-family: sans-serif;
  font-size: 0.8rem;
  letter-spacing: 1px;
}

caption {
  caption-side: bottom;
  padding: 10px;
  font-weight: bold;
}

thead,
tfoot {
  background-color: rgb(228 240 245);
}
.w-300 {
  width: 300px;
}

th,
td {
  border: 1px solid rgb(160 160 160);
  padding: 8px 10px;
  min-height: 34px;
}

td:last-of-type {
  text-align: center;
}

tbody > tr:nth-of-type(even) {
  background-color: rgb(237 238 242);
}

.func {
  position: relative;
  padding: 16px;
  border-radius: 16px;
  border: 1px solid;
  background-color: #eee;
}
.half-func {
  width: 48%;
  display: inline-block;
  position: relative;
  padding: 16px;
  border-radius: 16px;
  border: 1px solid;
  background-color: #eee;
  box-sizing: border-box;
}
.func-content {
  display: flex;
  justify-content: space-between;
}
.half-func .func-content {
  flex-direction: column;
}
.wrapper {
  display: flex;
  justify-content: space-between;
}
select {
  font-size: 16px;
}
.btns {
  display: flex;
  padding: 16px 24px;
  justify-content: space-between;
}

.footer-btn {
  display: block;
  margin: 8px auto;
}
</style>
