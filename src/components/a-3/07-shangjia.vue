<template>
  <el-table :data="myData" style="width: 80%;margin-top: 20px;">
    <el-table-column prop="net" label="设备类型" width="150"/>
    <el-table-column prop="ip" label="设备型号" width="150"/>
    <el-table-column prop="time" label="上架时间" width="150" align="center"/>
    <el-table-column prop="msg" label="负责人" width="120"/>
    <el-table-column prop="zhu" label="备注"  width="80" align="center"/>

    <el-table-column align="center" width="180">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索设备"/>
      </template>
      <template #default="scope">
        <el-button type="success" size="small">上架</el-button>
        <el-button
            size="small"
            type="danger"
        >下架
        </el-button
        >
      </template>
    </el-table-column>
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
      'net|1': ['存储型服务器', '安全设备', '网络设备'],
      'ip|1': [' 计算型服务器', '存储型服务器', '安全资源', '网络设备'],
      'xieyi|1': ['HTTP', 'SSL', 'HTTPS', 'TCP', 'UDP'],
      time: `${2022}-@date("MM-dd")`,

      'msg|1': ['管理员', '用户'],
      'duankou|1': ['虚拟端口', '物理端口'],
      zhu: '无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
