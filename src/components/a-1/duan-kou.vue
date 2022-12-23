<template>
  <div class="label-title" style="margin-top: 30px;">
    端口管理
  </div>

  <!--  系统名下拉框-->
  <div style="margin: 20px;">
    <span style="font-weight: bold;font-size: 15px">系统名称：</span>
    <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
      <el-option
          v-for="item in options"
          :key="item.value"
          :label="item.label"
          :value="item.value"
      />
    </el-select>
  </div>

  <el-table :data="myData" stripe style="width: 80%;margin-top: 20px;">
    <el-table-column prop="net" label="网络环境" width="180"  />
    <el-table-column prop="ip" label="ip" width="180" />
    <el-table-column prop="xieyi" label="协议" />
    <el-table-column prop="time" label="交互时间" />
    <el-table-column prop="duankou" label="端口环境" />
    <el-table-column prop="msg" label="备注" />

    <el-table-column label="Operations">
      <template #default="scope">
        <el-button size="small"
        >编辑</el-button
        >
        <el-button
            size="small"
            type="danger"
        >删除</el-button
        >
      </template>
    </el-table-column>
  </el-table>
</template>

<script setup>
import Mock from "mockjs";

const value = $ref('')
const options = [
  {
    value: 'Option1',
    label: 'Option1',
  }]

const myData = Mock.mock({
  'data|9-10':   [
    {
      net:'windows',ip:'@ip','xieyi|1':['HTTP','SSL', 'HTTPS', 'TCP', 'UDP'],time:'@datetime', 'msg|1':['管理员', '用户'],'duankou|1':['虚拟端口','物理端口']
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
