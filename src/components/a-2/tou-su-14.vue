<template>
  <div class="title_b">
    投诉处理
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;">
      <sapn>云服务商：</sapn>
      <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>

      <el-button type="success" plain style="margin-left: 20px;">新增</el-button>
    </div>
  </div>

  <el-table
      :data="myData"
      :row-class-name="tableRowClassName"
      style="width: 100%;margin-top: 20px;margin-left: 70px;"
  >
    <el-table-column prop="name" label="云服务商" width="120"/>
    <el-table-column prop="xin" label="是否信创" width="120"/>
    <el-table-column prop="xieyi" label="联系方式" width="130"/>
    <el-table-column prop="bei" label="投诉缘由" width="140">
      <template #default="scope">
        <el-button size="small">预览</el-button>
      </template>
    </el-table-column>
    <el-table-column prop="zhu" label="备注" width="120"/>

    <el-table-column label="操作" width="180">
      <template #default="scope">
        <el-button size="small">操作</el-button>
        <el-button type="danger" size="small">删除</el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-button type="primary" style="margin-left: 25%;margin-top: 10px;width: 90px;" >提交</el-button>

</template>

<script setup>
import Mock from "mockjs";

Mock.Random.extend({
  phone: function () {
    let phonePrefixs = ['132', '135', '189'] // 自己写前缀哈
    return this.pick(phonePrefixs) + Mock.mock(/\d{8}/) //Number()
  }
})

const myData = Mock.mock({
  'data|5-7': [
    {
      'name|1':['鲲鹏云','城运云'],
      net: '@ip',
      'xin|1':['是','否'],
      xieyi:['@phone'],
      time: '@datetime',
      bei: '无',
      lian:'@cword(2,3)',
      zhu:'无'
    }
  ]

}).data

const tableRowClassName = ({row, rowIndex,}) => {
  for (let i=1;i<100;i++){
    if (rowIndex === 0) {
      return 'success-row'
    } else if (rowIndex === i*2) {
      return 'success-row'
    }else if(rowIndex === i){
      return 'warning-row'
    }
  }
  return ''
}
</script>

<style scoped lang='less'>

</style>
