<template>
  <el-button type="success">新增</el-button>

  <el-table :data="myData" style="width: 90%;margin-top: 20px;">
    <el-table-column prop="net" label="系统名称" width="100"/>
    <el-table-column prop="ip" label="ip" width="160" align="center"/>
    <el-table-column prop="lei" label="测试类型" width="120"/>
    <el-table-column prop="xieyi" label="协议" width="100"/>
    <el-table-column prop="lian" label="测试人员" width="100"/>
    <el-table-column prop="time" label="测试时间" width="120"/>
    <el-table-column label="备注" prop="zhu"  width="80"/>

    <el-table-column align="center" width="160">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索系统" />
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

  <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 25%;">确认提交</el-button>
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

const ren = $ref(['张行','李扫','王炊亚','何威威'])

const myData = Mock.mock({
  'data|6-7': [
    {
      'net|1': ['windows','linux'],
      ip: '@ip',
      'lei|1':['功能测试','性能测试','可靠性测试','部署测试'],
      'xieyi|1': ['HTTP', 'SSL', 'HTTPS', 'TCP', 'UDP'],
      time:  `${2022}-@date("MM-dd")`,

      lian:`${'王'}@cword(1,2)`,
      'duankou|1': ['虚拟端口', '物理端口'],
      zhu:'无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
