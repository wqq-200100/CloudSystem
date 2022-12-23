<template>
  <el-button type="danger">投诉</el-button>

  <el-table :data="myData" style="width: 90%;margin-top: 20px;">
    <el-table-column prop="net" label="云服务商" width="100"/>
    <el-table-column prop="ip" label="投诉电话" width="120" align="center"/>
    <el-table-column prop="xinchuang" label="是否信创" align="center" width="120"/>
    <el-table-column prop="xieyi" label="投诉人" width="80"/>
    <el-table-column prop="time" label="投诉时间" width="120" align="center"/>

    <el-table-column label="投诉理由" width="120">
      <template #default="scope">
        <el-button type="info" plain>预览</el-button>
      </template>
    </el-table-column>

    <el-table-column label="备注" prop="zhu"  width="80"/>

    <el-table-column align="center" width="160">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索服务商" />
      </template>
      <template #default="scope">
        <el-button type="success"
        >处理</el-button
        >
        <el-button
            type="danger"
        >删除</el-button
        >
      </template>
    </el-table-column  >
  </el-table>

  <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 35%;">确认提交</el-button>
</template>

<script setup>
import Mock from "mockjs";
import {computed} from "vue";

Mock.Random.extend({
  phone: function () {
    let phonePrefixs = ['132', '135', '189'] // 自己写前缀哈
    return this.pick(phonePrefixs) + Mock.mock(/\d{8}/) //Number()
  }
})

const myData = Mock.mock({
  'data|5-6': [
    {
      'net|1': ['鲲鹏云','城运云'],
      ip:'@phone',
      'lei|1':['功能测试','性能测试','可靠性测试','部署测试'],
      xieyi:`${'李'}@cword(1,2)`,
      'xinchuang|1':['是','否'],
      time:  `${2022}-@date("MM-dd")`,

      lian:'@cword(2,3)',
      'duankou|1': ['虚拟端口', '物理端口'],
      zhu:'无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
