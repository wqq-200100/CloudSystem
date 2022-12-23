<template>
  <div class="title_b">
    数据交互
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;">
      联系人：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      联系方式：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;
      <el-button type="primary">新增</el-button>
    </div>
  </div>

  <el-table
      :data="myData"
      :row-class-name="tableRowClassName"
      style="width: 100%;margin-top: 20px;"
  >
    <el-table-column prop="net" label="ip" width="140"/>
    <el-table-column prop="ip" label="网络环境" width="100"/>
    <el-table-column prop="xieyi" label="协议" width="80"/>
    <el-table-column prop="time" label="申请时间" width="180"/>
    <el-table-column prop="bei" label="备注" width="80"/>

    <el-table-column label="操作" width="180">
      <template #default="scope">
        <el-button size="small">修改
        </el-button>
        <el-button
            size="small"
            type="danger">删除
        </el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-button type="primary" style="margin-left: 18%;margin-top: 10px;width: 90px;" >提交</el-button>

</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|6-7': [
    {
      net: '@ip',
      'ip|1': ['windows', 'linux'],
      'xieyi|1': ['TCP', 'HTTPS','HTTP'],
      time: '@datetime',
      bei: '无'
    }
  ]

}).data

const tableRowClassName = ({row, rowIndex,}) => {
  for (let i = 1; i < 100; i++) {
    if (rowIndex === 0) {
      return 'success-row'
    } else if (rowIndex === i * 2) {
      return 'success-row'
    } else if (rowIndex === i) {
      return 'warning-row'
    }
  }
  return ''
}
</script>

<style scoped lang='less'>

</style>
