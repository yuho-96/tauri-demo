<!--
 * @Author: liuyuhao
 * @Date: 2024-03-06 18:03:46
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-12 18:15:38
 * @Description: file description
-->
<template>
  <div class="root center-box">
    <div class="title mb8">预警信息</div>
    <table class="mb8" align="center">
      <thead>
        <tr>
          <th scope="col">type</th>
          <th scope="col">min</th>
          <th scope="col">max</th>
          <th scope="col">timeDiv</th>
          <th scope="col">dateDiv</th>
        </tr>
      </thead>
      <tbody align="center">
        <tr>
          <th scope="row">空气温度过高</th>
          <td>18摄氏度</td>
          <td>22摄氏度</td>
          <td>15-16</td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">-</th>
          <td>{{ '-' }}</td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">-</th>
          <td>{{ '-' }}</td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">-</th>
          <td>{{ '-' }}</td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">-</th>
          <td>{{ '-' }}</td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">-</th>
          <td>{{ '-' }}</td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
      </tbody>
    </table>
    <div class="bt8 func">
      <div class="">功能操作:</div>
      <button class="ml8">修改</button>
      <button class="ml8">删除</button>
      <button class="ml8">刷新列表</button>
    </div>
    <div class="fields-box">
      <div v-for="(field, i) in fields" :key="i" :class="['common-field mt8 mb8', field.className]">
        <span>{{ field.label }}</span>
        ：
        <span class="value">{{ field.value }}</span>
      </div>
    </div>
    <div class="btn-box mt8 mb8">
      <button>提交</button>
    </div>
  </div>
</template>

<script setup>
const fields = [
  {
    label: '字段关键词',
    value: '空气温度过高',
    className: 'row-24',
  },
  {
    label: '时间区间',
    value: '空气温度过高',
  },
  {
    label: '最大值',
    value: '22摄氏度',
  },
  {
    label: '季节选择',
    value: '--',
  },
  {
    label: '最小值',
    value: '18摄氏度',
  },
  {
    label: '预警提示内容',
    value: '空气温度大于最适温度',
    className: 'row-24',
  },
];
</script>
<style scoped>
.title {
  width: 100%;
  background-color: steelblue;
  font-size: 20px;
  padding: 12px;
  font-weight: bold;
  border-radius: 16px;
  color: #fff;
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
.fields-box {
  display: flex;
  flex-wrap: wrap;
}
.common-field {
  width: 50%;
}
.row-24 {
  width: 100%;
}
.value {
  display: inline-block;
  padding: 0 16px;
  background-color: skyblue;
  border-radius: 8px;
  color: #fff;
}
.btn-box {
  text-align: center;
}
</style>
