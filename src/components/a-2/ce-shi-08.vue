<template>
  <div class="title_b">
    安全测试
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;">
      测试人员：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      测试类型：<el-select v-model="value" class="m-2" placeholder="请选择测试类型" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;


      <sapn>系统名称：</sapn>
      <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
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
        <el-button >编辑</el-button>
        <el-button type="danger" >删除</el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-button type="primary" style="margin-left: 32%;margin-top: 10px;width: 90px;">提交</el-button>

</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|12': [
    {
      'name|1': ['linux', 'windows'],
      net: '@ip',
      'lei|1':['功能测试','性能测试','可靠性测试','部署测试'],
      'xieyi|1': ['TCP', 'HTTPS', 'HTTP'],
      time: '@datetime',
      bei: '无',
      'lian|1': `${'胡'}@cword(1,2)`
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
