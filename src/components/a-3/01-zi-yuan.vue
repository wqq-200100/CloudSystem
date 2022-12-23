<template>
  <el-button type="warning" >信创资源</el-button>
  <el-button type="warning" >非信创资源</el-button>
          <el-button type="primary">新增</el-button>


  <el-table :data="myData" style="width: 80%;margin-top: 20px;" >
    <el-table-column prop="lian" label="业务部门" width="120" />
    <el-table-column prop="name" label="云服务商" width="120" />
    <el-table-column prop="xin" align="center" label="是否信创" width="80" />
    <el-table-column prop="time" label="申请时间" align="center" width="180" />
    <el-table-column align="center" width="180" label="操作">
      <template #default="scope">
        <el-button type="success" >编辑</el-button>
        <el-button type="danger" >删除</el-button>
      </template>
    </el-table-column  >
  </el-table>

  <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 17%;">确认提交</el-button>

</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|5-7': [
    {
      'name|1':['鲲鹏云','城运云'],
      net: '@ip',
      'xin|1':['是','否'],
      xieyi:['@phone'],
      time:  `${2022}-@date("MM-dd")`,
      bei: '无',
      'lian|1':['市大数据中心',' 市卫健委','市场监管局','市住建局'],
      zhu:'无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
