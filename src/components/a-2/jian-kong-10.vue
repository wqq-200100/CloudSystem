<template>
  <div class="title_b">
    异常监控
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;">
      <sapn>云服务商：</sapn>
      <el-select v-model="value" class="m-2" placeholder="请选择" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>

      <el-button type="primary" style="margin-left: 20px;">搜索</el-button>
    </div>
  </div>

  <el-tabs
      v-model="activeName"
      class="demo-tabs"
      style="margin-top: 20px;margin-left: 20px;"
  >
    <el-tab-pane label="云主机" name="first">
      <div style="margin-top: 10px;">资源申请</div>
      <el-table
          :data="myData"
          :row-class-name="tableRowClassName"
          style="width: 100%;margin-top: 20px;"
      >
        <el-table-column prop="name" label="系统名称" width="120"/>
        <el-table-column prop="net" label="ip" width="160"/>
        <el-table-column prop="lei" label="测试类型" width="120"/>
        <el-table-column prop="xieyi" label="协议" width="120"/>
        <el-table-column prop="lian" label="测试人员" width="120"/>
        <el-table-column prop="time" label="测试时间" width="180"/>
        <el-table-column prop="bei" label="备注" width="100"/>

        <el-table-column label="操作" width="180">
          <template #default="scope">
            <el-button type="danger" size="small">删除</el-button>
          </template>
        </el-table-column>
      </el-table>

      <div style="margin-top: 10px;">云服务商</div>
      <el-table
          :data="myData"
          :row-class-name="tableRowClassName"
          style="width: 100%;margin-top: 20px;"
      >
        <el-table-column prop="name" label="系统名称" width="120"/>
        <el-table-column prop="net" label="ip" width="160"/>
        <el-table-column prop="lei" label="测试类型" width="120"/>
        <el-table-column prop="xieyi" label="协议" width="120"/>
        <el-table-column prop="lian" label="测试人员" width="120"/>
        <el-table-column prop="time" label="测试时间" width="180"/>
        <el-table-column prop="bei" label="备注" width="100"/>

        <el-table-column label="操作" width="180">
          <template #default="scope">
            <el-button type="danger" size="small">删除</el-button>
          </template>
        </el-table-column>
      </el-table>

    </el-tab-pane>
    <el-tab-pane label="物理机" name="second">物理机</el-tab-pane>
    <el-tab-pane label="存储资源" name="third">存储资源</el-tab-pane>
  </el-tabs>


  <el-button type="success" style="margin-left: 30%;margin-top: 20px;">对比详情</el-button>

</template>

<script setup>
import Mock from "mockjs";

const activeName = $ref('first')

const myData = Mock.mock({
  'data|4-5': [
    {
      'name|1': ['linux', 'windows'],
      net: '@ip',
      'lei|1':['功能测试','性能测试','可靠性测试','部署测试'],
      'xieyi|1': ['TCP', 'HTTPS', 'HTTP'],
      time: '@datetime',
      bei: '无',
      'lian|1': `${'黄'}@cword(1,2)`,
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
