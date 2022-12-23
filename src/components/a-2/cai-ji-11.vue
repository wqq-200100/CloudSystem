<template>
  <div class="title_b">
    数据采集
  </div>
  <div style="display: flex;margin-top: 50px;">
    <a3 style="height: 360px;width: 360px;"/>
    <a4 style="height: 360px;width: 360px;"/>
  </div>

  <div style="display: flex;align-items: center;margin-top: -75px;">
    <a5 style="height: 360px;width: 460px;"/>
    <el-button type="primary" plain style="margin-left: 40px;">查看详情</el-button>
  </div>

  <el-button type="primary" style="margin-left: 18%;width: 90px;">提交</el-button>

</template>

<script setup>
import Mock from "mockjs";
import a3 from "../../charts/a3.vue";
import a4 from "../../charts/a4.vue";
import a5 from "../../charts/a5.vue";


const myData = Mock.mock({
  'data|12': [
    {
      'name|1': ['linux', 'windows'],
      net: '@ip',
      'lei|1': ['功能测试', '性能测试', '可靠性测试', '部署测试'],
      'xieyi|1': ['TCP', 'HTTPS', 'HTTP'],
      time: '@datetime',
      bei: '无',
      lian: '@cword(2,3)'
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
