<template>
  <div class="label-title" style="margin-top: 30px;">
    数据交互
  </div>

  <div style="margin: 20px;">
              <div style="margin-top: 10px;">
                联系人：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                负责人：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                联系方式：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              </div>
  </div>

  <el-table :data="myData" stripe style="width: 80%;margin-top: 20px;">
    <el-table-column prop="net" label="网络环境" width="180"  />
    <el-table-column prop="ip" label="ip" width="180" />
    <el-table-column prop="xieyi" label="协议" />
    <el-table-column prop="time" label="交互时间" />
    <el-table-column prop="msg" label="备注" />
  </el-table>
</template>

<script setup>
import Mock from "mockjs";


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
