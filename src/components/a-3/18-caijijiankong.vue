<template>
<!--  <div style="font-weight: bold">-->
<!--    采集监控-->
<!--  </div>-->
<!--  <a10 style="width: 900px;height: 500px;"/>-->
<!--  <div style="font-weight: bold">NAT追踪</div>
  <el-table :data="myData" style="width: 100%;margin-top: 20px;" :row-class-name="tableRowClassName">
    <el-table-column label="服务端" prop="jiexi2" width="140" align="center" />
    <el-table-column label="客户端" prop="jiexi3" width="160" align="center" />
    <el-table-column label="流日志特征分组" prop="jiexi4" width="160" align="center" />
    <el-table-column label="TCP重传比例(%)" prop="number" width="140" align="center" />
    <el-table-column label="平均应用延时(ms)" prop="jiexi6" width="140" align="center" />
  </el-table>-->
  <div style="font-weight: bold">流量统计表</div>
    <el-table :data="myData" style="width: 100%;margin-top: 20px;" :row-class-name="tableRowClassName">
    <el-table-column label="服务端ip" prop="jiexi2" width="140" align="center" />
    <el-table-column label="客户端ip" prop="jiexi3" width="160" align="center" />
    <el-table-column label="请求方法" prop="get" width="160" align="center" />
    <el-table-column label="路径" prop="path" width="140" align="center" />
    <el-table-column label="状态" prop="jiexi6" width="140" align="center" />
    <el-table-column label="响应码" prop="ma" width="140" align="center" />
    <el-table-column label="路径统计位置" prop="wei" width="140" align="center" />
  </el-table>

<!--  <a10 style="width: 1300px;height: 300px;"/>-->
<!--  <el-table :data="myData" style="width: 100%;margin-top: 20px;" :row-class-name="tableRowClassName">
    <el-table-column label="开始时间" prop="time" width="140" align="center" />
    <el-table-column label="客户端" prop="jiexi3" width="160" align="center" />
    <el-table-column label="服务端" prop="jiexi2" width="160" align="center" />
    <el-table-column label="网络协议" prop="tcp" width="140" align="center" />
    <el-table-column label="客户端口" prop="duan" width="140" align="center" />
    <el-table-column label="服务端口" prop="fu" width="140" align="center" />
    <el-table-column label="路径统计位置" prop="wei" width="140" align="center" />
    <el-table-column label="最大tcp建联时流（ms）" prop="number" width="150" align="center" />
  </el-table>-->
</template>

<script setup>
import a8 from "../../charts/a8.vue";
import a9 from "../../charts/a9.vue";
import a10 from "../../charts/a10.vue";
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
  'data|6-9': [
    {
      jiexi2:'@ip',
      jiexi3:'@ip',
      'jiexi4|1':['tcp 80','tcp 22','tcp 20'],
      "number|1-100.1-2": 1,
      jiexi6:'正常',
      'get|1':['GET','POST'],
      path:'/v2/code/',
      ma:'200',
      'wei|1':['本机网卡','客户端网卡'],
      time:  `${2022}-@date("MM-dd")`,
      'tcp|1':['tcp','http','udp'],
      'duan|1':[8080,212,3421],
      'fu|1':[80,1232,234]
    }
  ],

}).data
</script>

<style scoped lang='less'>

</style>
