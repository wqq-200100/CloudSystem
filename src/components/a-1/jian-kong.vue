<template>
  <div class="label-title">
    资源异常监控
  </div>
  <el-tabs type="border-card" style="margin: 30px 25px;height:100%;">
    <el-tab-pane label="云主机">
      <div style="font-weight: bold;font-size: 15px;margin-left: 14px;margin-top: 10px;">申请资源：</div>
      <el-table :data="myData" stripe style="width: 65%;margin-top: 20px;">
        <el-table-column prop="net" label="系统名称" width="120"/>
        <el-table-column prop="ip" label="ip" width="130"/>
        <el-table-column prop="xin" label="cpu" width="120"/>
        <el-table-column prop="neicun" label="内存" width="150"/>
        <el-table-column prop="xieyi" label="存储" width="120"/>
        <el-table-column prop="time" label="申请时间" width="180"/>
        <el-table-column prop="msg" label="联系方式" width="120"/>
      </el-table>

      <div style="font-weight: bold;font-size: 15px;margin-left: 14px;margin-top: 20px;">云服务商：</div>
      <el-table :data="myData1" stripe style="width: 65%;margin-top: 20px;">
        <el-table-column prop="net" label="系统名称" width="120"/>
        <el-table-column prop="ip" label="ip" width="130"/>
        <el-table-column prop="xin" label="cpu" width="120"/>
        <el-table-column prop="neicun" label="内存" width="150"/>
        <el-table-column prop="xieyi" label="存储" width="120"/>
        <el-table-column prop="time" label="申请时间" width="180"/>
        <el-table-column prop="msg" label="联系方式" width="120"/>
      </el-table>

      <button style="font-weight: bold;font-size: 15px;margin-left: 14px;margin-top: 20px;">数据对比详情</button>

    </el-tab-pane>
    <el-tab-pane label="物理机">物理机</el-tab-pane>
    <el-tab-pane label="存储资源">存储资源</el-tab-pane>
  </el-tabs>
</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|3': [
    {
      net: 'windows',
      ip: '@ip',
      'xieyi|1': ['4T', '8T', '16T'],
      time: '@datetime',
      msg: '@string(number,11)',
      duankou: '@cword(2,3)',
      'xin|1': ['64G','128G','265G'],
      'neicun|1': ['64G','128G','265G'],
    }
  ]

}).data
const myData1 = Mock.mock({
  'data|3': [
    {
      net: 'Linux',
      ip: '@ip',
      'xieyi|1': ['4T', '8T', '16T'],
      time: '@datetime',
      msg: '@string(number,11)',
      duankou: '@cword(2,3)',
      'yali|1': ['64G','128G','265G'],
      'neicun|1': ['64G','128G','265G'],
      'xin|1': ['是','否'],
    }
  ]

}).data

</script>

<style scoped lang='less'>

</style>
