<template>
  <div style="font-weight: bold">
<!--    流量数据-->
<!--    知识图谱-->
    流量属性
  </div>

<!--  <el-tabs type="border-card"
           style="margin: 30px 25px;height:100%;">
    <el-tab-pane label="物理网络">
      <el-table :data="myData3"
                style="width: 65%;margin-top: 20px;"
                :row-class-name="tableRowClassName"
      >
        <el-table-column prop="net" label="客户端ip" width="140"/>
        <el-table-column prop="ip" label="服务端ip" width="140"/>
        <el-table-column prop="xin" label="发送比特值(BT/s)" width="140" align="center"/>
        <el-table-column prop="xieyi" label="建连-累积失败比例(%)" width="150" align="center"/>
        <el-table-column prop="yan" label="平均TCP建连时延均值(ms)" width="140"/>
        <el-table-column prop="time" label="发送字节" width="120"/>
        <el-table-column prop="msg" label="接收字节" width="120"/>
      </el-table>
    </el-tab-pane>
    <el-tab-pane label="虚拟网络">物理机</el-tab-pane>
    <el-tab-pane label="容器网络">存储资源</el-tab-pane>
  </el-tabs>-->

<!--  <el-table :data="myData" style="width: 90%;margin-top: 20px;" :row-class-name="tableRowClassName">
    <el-table-column label="区域" prop="net"  width="80"/>
    <el-table-column label="可用区" prop="yu" width="120" />
    <el-table-column label="资源池" prop="chi" width="130" align="center" />
    <el-table-column label="容器集群" prop="ji" width="140" align="center" />
    <el-table-column label="租户" prop="zhu" width="80" />
  </el-table>-->

  <el-table :data="myData1" style="width: 90%;margin-top: 20px;" :row-class-name="tableRowClassName">
    <el-table-column label="IP类型" prop="name"  width="100"/>
    <el-table-column label="网络协议" prop="net" width="100" />
    <el-table-column label="服务端口特征" prop="ren" width="120" align="center" />
    <el-table-column label="流量访问关系" prop="xi" width="120" align="center" />
    <el-table-column label="流量监控指标" prop="zhu" width="120" align="center" />
  </el-table>

</template>

<script setup>
import Mock from "mockjs";
const myData3 = Mock.mock({
  'data|6': [
    {
      'name|1': ['鲲鹏云', '城运云','新华三云','浪潮云','曙光云'],
      net:'@ip',
      ip:'@ip',
      "xin|1-100.1-2": 1,
      "xieyi|1-10.1-2": 1,
      "yan|100-150.1-2": 1,
      "time|1-1000": 1,
      "msg|1-1000": 1,
    }
  ],

}).data


const myData = Mock.mock({
  'data|6-9': [
    {
      'name|1': ['鲲鹏云', '城运云','新华三云','浪潮云','曙光云'],
      'net|1': ['华南地区', '华东地区', '华北地区'],
      'yu|1': ['北部', '东部', '西部','南部'],
      'xin|1': ['是', '否'],
      'xieyi|1': ['tcp','http','https','udp'],
      time:  `${2022}-@date("MM-dd")`,
      ren:`${'张'}@cword(1,2)`,
      bei: '无',
      lian: '@cword(2,3)',
      'zhu|1': `${'李'}@cword(1,2)`,
      'chi|1':['服务器资源池','私有资源池'],
      'ji|1':['Docker Swarm','Core OS','Kubernetes']
    }
  ]

}).data
const myData1 = Mock.mock({
  'data|6-9': [
    {
      'name|1': ['A类', 'B类','C类'],
      'net|1':['tcp','http','https','udp'],
      'yu|1': ['北部', '东部', '西部','南部'],
      'xin|1': ['是', '否'],
      'xieyi|1': ['tcp','http','https','udp'],
      time:  `${2022}-@date("MM-dd")`,
      'ren|1':['虚拟端口','物理端口'],
      bei: '无',
      lian: '@cword(2,3)',
      'zhu|1': ['网络出带宽','网络入带宽','带宽使用率'],
      'chi|1':['服务器资源池','私有资源池'],
      'ji|1':['Docker Swarm','Core OS','Kubernetes'],
      'xi|1':['管理员','用户']
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
.el-table .warning-row {
  background: oldlace;
}

.el-table .success-row {
  background: #f0f9eb;
}
</style>
