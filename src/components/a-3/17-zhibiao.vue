<template>
<div style="display: flex">
<!--  <a8 style="width:700px;height: 400px;"/>-->
<!--  <a9 style="width:400px;height: 400px;"/>-->
</div>

  <el-table :data="myData" style="width: 100%;margin-top: 20px;" :row-class-name="tableRowClassName">
<!--    <el-table-column label="HTTP时延(S)" prop="number"  width="120" align="center"/>-->
<!--    <el-table-column label="DNS时延(s)" prop="number" width="120" align="center" />-->
<!--    <el-table-column label="支持解析HTTP V2协议" prop="jiexi" width="130" align="center" />-->
        <el-table-column label="TCP客户端建连失败" prop="jiexi1" width="100" align="center" >
          <template #default="scope">
            <el-button plain size="small">详情</el-button>
          </template>
        </el-table-column>
        <el-table-column label="TCP服务端建连" prop="jiexi2" width="125" align="center" />
        <el-table-column label="TCP客户端传输异常" prop="jiexi3" width="160" align="center" />
        <el-table-column label="TCP服务端传输异常" prop="jiexi4" width="160" align="center" />
        <el-table-column label="TCP客户端半关" prop="jiexi5" width="130" align="center" />
        <el-table-column label="TCP服务端半关" prop="jiexi6" width="130" align="center" />
        <el-table-column label="TCP超时" prop="jiexi7" width="130" align="center" />
  </el-table>

</template>

<script setup>
import a8 from "../../charts/a8.vue";
import a9 from "../../charts/a9.vue";
import Mock from "mockjs";

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

const myData = Mock.mock({
  'data|6': [
    {
      'name|1': ['鲲鹏云', '城运云','新华三云','浪潮云','曙光云'],
      'net|1': ['服务器宕机', '服务器卡死', '网络故障', '应用故障', ' 其他故障 '],
      'xin|1': ['是', '否'],
      'xieyi|1': ['tcp','http','https','udp'],
      time:  `${2022}-@date("MM-dd")`,
      ren:`${'张'}@cword(1,2)`,
      bei: '无',
      lian: '@cword(2,3)',
      zhu: '无',
      "number|1-100.1-2": 1,
      'jiexi|1':['是','否'],
      'jiexi1|1':['是','否'],
      'jiexi2|1':['是','否'],
      'jiexi5|1':['是','否'],
      'jiexi6|1':['是','否'],
      'jiexi7|1':['是','否'],
      'jiexi3|1':['有','无'],
      'jiexi4|1':['有','无'],
    }
  ],

}).data
</script>

<style scoped lang='less'>

</style>
