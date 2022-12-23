<template>
  <el-button type="success">新增需求</el-button>

  <el-table :data="myData" style="width: 90%;margin-top: 20px;">
    <el-table-column prop="net" label="云服务商" width="100"/>
    <el-table-column prop="ip" label="系统类型" width="120"/>
    <el-table-column prop="xinchuang" label="是否信创" width="120"/>
    <el-table-column prop="xieyi" label="协议" width="100"/>

    <el-table-column label="需求" width="120">
      <template #default="scope">
        <el-button type="info" plain >预览</el-button>
      </template>
    </el-table-column>

    <el-table-column label="备注" prop="zhu"  width="80"/>

    <el-table-column align="right" width="160">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索服务商" />
      </template>
      <template #default="scope">
        <el-button type="success"  @click="handleEdit(scope.$index, scope.row)"
        >编辑</el-button
        >
        <el-button

            type="danger"
        >删除</el-button
        >
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
      'net|1': ['鲲鹏云','城运云'],
      'ip|1': ['linux','windows'],
      'lei|1':['功能测试','性能测试','可靠性测试','部署测试'],
      'xieyi|1': ['HTTP', 'SSL', 'HTTPS', 'TCP', 'UDP'],
      'xinchuang|1':['是','否'],
      time: '@datetime',
      lian:'@cword(2,3)',
      'duankou|1': ['虚拟端口', '物理端口'],
      zhu:'无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
