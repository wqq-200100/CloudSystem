<template>
  <div class="title_b">
    设备上下架
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;">

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
    <el-table-column prop="name" label="设备名称" width="120"/>
    <el-table-column prop="net" label="设备品牌" width="120"/>
    <el-table-column prop="gu" label="故障" width="120"/>
    <el-table-column prop="time" label="上架时间" width="180"/>
    <el-table-column prop="bei" label="备注" width="120"/>

    <el-table-column label="操作" width="180">
      <template #default="scope">
        <el-button type="success" size="small">上架</el-button>
        <el-button
            size="small"
            type="danger">下架
        </el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-button type="primary" style="margin-left: 21%;margin-top: 10px;width: 90px;" >提交</el-button>

</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|12': [
    {
      'name|1':['linux','windows'],
      'net|1': ['FAST','UBNT'],
      'gu|1':['服务器宕机', '服务器卡死', '网络故障', '应用故障', ' 其他故障 '],
      time: '@datetime',
      bei: '无',
      lian:'@cword(2,3)'
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
