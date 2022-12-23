<template>
  <el-button type="success" style="margin-left: 100px;margin-top: 30px;">对比详情</el-button>

  <el-tabs :tab-position="tabPosition" style="height: 100%;margin-top: 30px;" class="demo-tabs">
    <el-tab-pane label="云主机">
      <div style="font-weight: bold">资源申请:</div>
      <el-table :data="myData" style="width: 90%;margin-top: 20px;">
        <el-table-column prop="net" label="云服务商" width="100" align="center"/>
        <el-table-column prop="ip" label="系统类型" width="120" align="center"/>
        <el-table-column prop="dizhi" label="ip地址" width="140" align="center"/>
        <el-table-column prop="xinchuang" label="是否信创" width="120" align="center"/>

        <el-table-column label="备注" prop="zhu" width="80" align="center"/>

        <el-table-column align="center" width="160" label="操作">
          <template #default="scope">
            <el-button type="success">编辑</el-button>
            <el-button type="danger">删除</el-button>
          </template>
        </el-table-column>
      </el-table>

      <div style="font-weight: bold;margin-top: 30px;">云服务商:</div>
      <el-table :data="myData" style="width: 90%;margin-top: 20px;">
        <el-table-column prop="net" label="云服务商" width="100" align="center"/>
        <el-table-column prop="ip" label="系统类型" width="120" align="center"/>
        <el-table-column prop="dizhi" label="ip地址" width="140" align="center"/>
        <el-table-column prop="xinchuang" label="是否信创" width="120" align="center"/>

        <el-table-column label="备注" prop="zhu" width="80" align="center"/>

        <el-table-column align="center" width="160" label="操作">
          <template #default="scope">
            <el-button type="success">操作</el-button>
            <el-button  type="danger">删除</el-button>
          </template>
        </el-table-column>
      </el-table>
      <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 25%;">确认提交</el-button>

    </el-tab-pane>
    <el-tab-pane label="物理机">物理机</el-tab-pane>
    <el-tab-pane label="存储资源">存储资源</el-tab-pane>
  </el-tabs>
</template>

<script setup>
import Mock from "mockjs";
import {computed} from "vue";

const tabPosition = $ref('left')
const search = $ref('')
const filterTableData = computed(() =>
    myData.filter(
        (data) => !search || data.name.toLowerCase().includes(search.toLowerCase())
    )
)

const myData = Mock.mock({
  'data|4-5': [
    {
      'net|1': ['鲲鹏云', '城运云'],
      dizhi: '@ip',
      'ip|1': ['linux', 'windows'],
      'lei|1': ['功能测试', '性能测试', '可靠性测试', '部署测试'],
      'xieyi|1': ['HTTP', 'SSL', 'HTTPS', 'TCP', 'UDP'],
      'xinchuang|1': ['是', '否'],
      time: '@datetime',
      lian: '@cword(2,3)',
      'duankou|1': ['虚拟端口', '物理端口'],
      zhu: '无',

    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
