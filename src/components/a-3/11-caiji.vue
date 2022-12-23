<template>
    <el-table :data="tableData1" style="width: 30%;margin-top: 30px;">
      <el-table-column prop="names" label="设备名称" width="150"/>
      <el-table-column prop="num" label="数量" width="100"/>
      <el-table-column align="center" width="160" label="操作">
        <template #default="scope">
          <el-button type="success" @click="handleEdit(scope.$index, scope.row)">详情</el-button>
        </template>
      </el-table-column>
    </el-table>

</template>

<script setup>
import Mock from "mockjs";
import {computed} from "vue";


const tableData1 = [
  {
    names: '云服务器',
    num: '23台',
  },
  {
    names: '高性能服务器',
    num: '15台',

  },
  {
    names: '集中式存储',
    num: '29TB',

  },
  {
    names: '分布式存储',
    num: '40TB',

  },
  {
    num: '23台',
    names: '高性能服务器',

  },
  {
    num: '15台',
    names: '数据库',

  },
  {
    num: '19台',
    names: '网络地址',
  },
  {
    num: '21台',
    names: '操作系统',
  },
  {
    num: '33台',
    names: '入侵系统',
  },
  {
    num: '41台',
    names: '流量统计',
  },
  {
    num: '12台',
    names: '警告事件',
  }
]
const tableData = [

]
</script>

<style scoped lang='less'>

</style>
