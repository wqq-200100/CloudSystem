<template>
  <el-table :data="myData" style="width: 50%;margin-top: 20px;">
    <el-table-column label="操作系统" prop="name"  width="100" align="center"/>
    <el-table-column label="ip地址" prop="net"  width="150" align="center"/>
    <el-table-column label="当前版本" prop="xieyi" width="120" align="center"/>
    <el-table-column label="升级时间" prop="time" width="160" align="center" />
    <el-table-column label="备注" prop="zhu"  width="80" align="center"/>

    <el-table-column align="right" width="180">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索系统" />
      </template>
      <template #default="scope" >
        <el-button type="success" size="small">升级</el-button>
        <el-button size="small" type="danger">删除</el-button>
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
      name:'linux',
      net: '@ip',
      'xin|1': ['是', '否'],
      'xieyi|1': ['centos 7.6','centos 7.4'],
      time:  `${2022}-@date("MM-dd")`,

      bei: '无',
      lian: '@cword(2,3)',
      zhu: '无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
