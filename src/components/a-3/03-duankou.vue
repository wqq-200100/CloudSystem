<template>
  <el-table :data="myData" style="width: 50%;margin-top: 20px;">
    <el-table-column label="ip地址" prop="net"  width="160"/>
    <el-table-column label="端口号" prop="number" width="160"/>
    <el-table-column label="端口开通时间" prop="time" width="180" />
    <el-table-column label="备注" prop="zhu"  width="80"/>

    <el-table-column align="right" width="180">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索关键字" />
      </template>
      <template #default="scope">
        <el-button type="success" >编辑</el-button>
        <el-button type="danger" >删除</el-button>
      </template>
    </el-table-column  >
  </el-table>

  <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 20%;">确认提交</el-button>
</template>

<script setup>
import Mock from "mockjs";
import {computed} from "vue";

const search = $ref('')
const filterTableData = computed(() =>
    myData.filter(
        (data) => !search || data.name.toLowerCase().includes(search.toLowerCase())
    )
)

const myData = Mock.mock({
  'data|7-10': [
    {
      'name|1': ['鲲鹏云', '城运云'],
      net: '@ip',
      'xin|1': ['是', '否'],
      'xieyi|1': `${''}`,
      time:  `${2022}-@date("MM-dd")`,
      bei: '无',
      lian: '@cword(2,3)',
      zhu: '无',
      'number|1':['8080','30882','30880','443']
    },
  ]

}).data
</script>

<style scoped lang='less'>

</style>
