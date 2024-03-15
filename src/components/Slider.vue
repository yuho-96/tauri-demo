<!--
 * @Author: liuyuhao
 * @Date: 2024-03-08 16:05:30
 * @LastEditors: liuyuhao
 * @LastEditTime: 2024-03-08 17:59:31
 * @Description: file description
-->
<template>
  <div class="root shadow-border">
    <div class="title border-bottom-blue">服务器监听</div>
    <div class="mt8">
      监听端口
      <span class="port-text">8080</span>
    </div>
    <div class="btns title border-bottom-blue">
      <button>关闭</button>
      <button class="ml8">断开</button>
    </div>

    <div class="mt8 border-bottom-blue">消息发送</div>
    <div class="mt8 mb8">
      <input type="checkbox" name="send" />
      <label for="send" class="ml8">定时发送</label>
      <input class="ml8" style="width: 100px" type="text" value="1000" />
      <br />
      <div class="mt8 border-bottom-blue">
        <input checked class="mt8" type="checkbox" name="receive" />
        <label for="receive" class="ml8">16进制接收</label>
        <input class="ml8" checked type="checkbox" name="send16" />
        <label for="send16" class="ml8">16进制发送</label>
      </div>
    </div>
    <div>
      <div>
        <input class="mt8" type="checkbox" name="control" />
        <label for="control" class="ml8">Auto控制字符</label>
      </div>
      <div>
        <input class="mt8" type="checkbox" name="pouse" />
        <label for="pouse" class="ml8">暂停显示</label>
        <input class="ml8" type="checkbox" name="analogue" />
        <label for="analogue" class="ml8">模拟设备</label>
      </div>
    </div>

    <div class="mt8 border-bottom-blue">功能选择</div>
    <div class="fun-btns mt8">
      <button>
        <Icon icon="ri:download-2-fill" />
        保存
      </button>
      <button>
        <Icon icon="ri:delete-bin-7-line" />
        清空
      </button>
      <button>
        <Icon icon="ri:file-add-line" />
        添加
      </button>
      <button>
        <Icon icon="ri:database-2-fill" />
        数据库
      </button>
      <button>
        <Icon icon="ri:remote-control-fill" />
        远程控制
      </button>
      <button>
        <Icon icon="ri:alarm-warning-fill" color="#ff6251" />
        预警设备
      </button>
    </div>
  </div>
</template>

<script setup>
import { Icon } from '@iconify/vue';
</script>
<style scoped>
.root {
  width: 25%;
  padding: 16px;
  box-sizing: border-box;
  border-radius: 16px;
  background-color: #fff;
}
.border-bottom-blue {
  padding: 12px;
  border-bottom: 2px solid #eee;
}
.port-text {
  background-color: steelblue;
  color: #fff;
  display: inline-block;
  padding: 2px 16px;
  border-radius: 8px;
}
.btns {
  text-align: center;
}
.send-item {
  display: flex;
  flex-direction: row;
}
.fun-btns {
  display: flex;
  flex-direction: column;
}
.fun-btns button {
  margin-bottom: 8px;
}
</style>
