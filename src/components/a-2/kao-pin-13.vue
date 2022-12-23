<template>
  <div class="title_b">
    综合评分
  </div>

 <div style="display: flex;margin-top: 30px;">
   <a6 style="height: 300px;width: 460px;" :num="num" :title="title"/>
   <a6 style="height: 300px;width: 460px;margin-left: 50px;" :num="num1" :title="title1"/>
 </div>
  <el-button type="success" style="margin-left: 28%;margin-top: 40px;width: 80px;">更新</el-button>

<!--  <el-button type="primary" style="margin-left: 18%;width: 90px;">提交</el-button>-->

</template>

<script setup>
import Mock from "mockjs";
import a6 from "../../charts/a6.vue";

const num = $ref([90, 80, 100, 70, 65])
const title = $ref('2022年用户满意度')

const num1 = $ref([66, 87, 95, 70, 79])
const title1 = $ref('2022年设备排行')

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
