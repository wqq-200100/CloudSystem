<template>

  <div class="title_b">
    资源工单
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <span style="font-weight: bold;font-size: 15px">业务部门：</span>
    <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
      <el-option
          v-for="item in options"
          :key="item.value"
          :label="item.label"
          :value="item.value"
      />
    </el-select>
    <el-button type="primary" style="margin-left: 20px;">新增</el-button>

  </div>

  <el-tabs type="border-card" style="margin-top: 20px;width: 40%;">
    <el-tab-pane label="信创资源">
      <el-table
          :data="myData"
          style="width: 100%;margin-top: 20px;"
          :row-class-name="tableRowClassName"
      >
        <el-table-column prop="net" label="业务部门" width="120"/>
        <el-table-column prop="ip" label="是否信创" width="100"/>
        <el-table-column prop="xieyi" label="云服务商" width="140"/>
        <el-table-column prop="time" label="申请时间" width="180"/>
        <el-table-column prop="bei" label="备注" width="180"/>
      </el-table>
    </el-tab-pane>
    <el-tab-pane label="非信创资源">非信创资源</el-tab-pane>
  </el-tabs>
</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|4-6': [
    {
      'net|1': ['大数据中心','卫健委','市场监管局','市住建局'],
      'ip|1': ['是', '否'],
      'xieyi|1': ['鲲鹏云', '城运云'],
      time: '@datetime',
      'bei|1': ['管理员', '用户']
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
