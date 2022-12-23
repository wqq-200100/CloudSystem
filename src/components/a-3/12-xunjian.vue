<template>

  <el-table :data="myData" style="width: 80%;margin-top: 20px;">
    <el-table-column prop="net" label="品牌" width="80" align="center"/>
    <el-table-column prop="ip" label="主机cpu(G)" width="120" align="center"/>
    <el-table-column prop="time" label="内存(TB)" width="120" align="center"/>
    <el-table-column prop="msg1" label="硬盘数量（个）" width="125" align="center"/>
    <el-table-column prop="msg2" label="电源" width="100"/>
    <el-table-column prop="msg3" label="风扇" width="100"/>
    <el-table-column prop="msg4" label="事件" width="80"/>
    <el-table-column label="备注" prop="zhu"  width="80"/>

    <el-table-column align="center" width="160">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索品牌" />
      </template>
      <template #default="scope">
        <el-button type="success"
        >编辑</el-button
        >
        <el-button

            type="danger"
        >删除</el-button
        >
      </template>
    </el-table-column  >
  </el-table>

  <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 28%;">确认提交</el-button>
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
      'net|1': ['浪潮', '曙光'],
      'ip|1': ['64', '128', '256'],
      'time|1': ['64', '128', '256'],
      'msg1|1': ['1', '2', '3', '4'],
      msg2: '正常',
      msg3: '正常',
      'msg4|+1': 1,
      zhu:'无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
