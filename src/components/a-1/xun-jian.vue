<template>
  <div class="label-title">
    自动化巡检
  </div>

  <div style="margin: 20px;">
    <div style="margin-top: 10px;display: flex">
      <div style="margin-left: 60px;">
        <span style="font-weight: bold;font-size: 15px">品牌：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择机房" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <button style="background: #48b0f1;border: none;border-radius: 8px;width: 70px;height: 40px;margin:1px 10px;">
        搜索
      </button>
      <button style="background: #b1b6b9;border: none;border-radius: 8px;width: 70px;height: 40px;margin:1px 10px;">
        重置
      </button>
    </div>
  </div>

  <el-table :data="myData1" stripe style="width: 80%;margin-top: 20px;margin-left: 80px;">
    <el-table-column prop="net" label="品牌" width="80"/>
    <el-table-column prop="ip" label="主机cpu" width="120"/>
    <el-table-column prop="time" label="内存" width="80"/>
    <el-table-column prop="msg1" label="硬盘数量" width="80"/>
    <el-table-column prop="msg2" label="电源" width="80"/>
    <el-table-column prop="msg3" label="风扇" width="80"/>
    <el-table-column prop="msg4" label="事件" width="80"/>

    <el-table-column label="操作" width="190">
      <template #default="scope">
        <el-button size="small">修改
        </el-button>
        <el-button
            size="small"
            type="danger">删除
        </el-button>
      </template>
    </el-table-column>
  </el-table>

</template>

<script setup>
import Mock from "mockjs";

const myData1 = Mock.mock({
  'data|9-10': [
    {
      'net|1': ['浪潮', '曙光'],
      'ip|1': ['64', '128', '256'],
      'time|1': ['64', '128', '256'],
      'msg1|1': ['1', '2', '3', '4'],
      msg2: '同源',
      msg3: '正常',
      'msg4|+1': 1,
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
