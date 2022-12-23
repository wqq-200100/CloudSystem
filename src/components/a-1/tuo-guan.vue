<template>
  <div class="label-title">
    托管设备上下架
  </div>

  <div style="display: flex">
    <div style="margin-top: 50px;margin-left: 10px;">
      <span style="font-weight: bold;font-size: 15px">服务商名称：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择服务商" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>

    <div style="margin-top: 50px;margin-left: 60px;">
      <span style="font-weight: bold;font-size: 15px">机房名称：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择机房" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>

    <div class="demo-range" style="margin-top: 50px;margin-left: 60px;">
      <span style="font-weight: bold;font-size: 15px">上架时间：</span>
      <el-time-picker
          v-model="value1"
          is-range
          range-separator="To"
          start-placeholder="上架时间"
          end-placeholder="下架时间"
      />
    </div>
  </div>

  <el-table :data="myData" stripe style="width: 80%;margin-top: 20px;">
    <el-table-column prop="net" label="设备类型" width="120"/>
    <el-table-column prop="ip" label="设备型号" width="180"/>
    <el-table-column prop="time" label="上架时间" width="180"/>
    <el-table-column prop="msg" label="负责人" width="120"/>

    <el-table-column label="操作">
      <template #default="scope">
        <el-button size="small"
        >上架
        </el-button
        >
        <el-button
            size="small"
            type="danger"
        >下架
        </el-button
        >
      </template>
    </el-table-column>
  </el-table>
</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|9-10': [
    {
      net: 'windows',
      'ip|1': ['云服务器_QVM_云主机', '云存储_对象存储'],
      'xieyi|1': ['HTTP', 'SSL', 'HTTPS', 'TCP', 'UDP'],
      time: '@datetime',
      'msg|1': ['管理员', '用户'],
      'duankou|1': ['虚拟端口', '物理端口']
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
