<template>
  <div class="title_b">
    自动巡检
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;">
      <sapn>品牌：</sapn>
      <el-select v-model="value" class="m-2" placeholder="请选择品牌" size="large">
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
      style="width: 100%;margin-top: 20px;margin-left: 70px;"
  >
    <el-table-column prop="net" label="品牌" width="80"/>
    <el-table-column prop="ip" label="主机cpu(G)" width="120"/>
    <el-table-column prop="time" label="内存(TB)" width="120"/>
    <el-table-column prop="msg1" label="硬盘数量（个）" width="125"/>
    <el-table-column prop="msg2" label="电源" width="100"/>
    <el-table-column prop="msg3" label="风扇" width="100"/>
    <el-table-column prop="msg4" label="事件" width="80"/>

    <el-table-column label="操作" width="180">
      <template #default="scope">
        <el-button size="small">编辑</el-button>
        <el-button type="danger" size="small">删除</el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-button type="primary" style="margin-left: 27%;margin-top: 10px;width: 90px;" >提交</el-button>

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
      'net|1': ['浪潮', '曙光'],
      'ip|1': ['64', '128', '256'],
      'time|1': ['64', '128', '256'],
      'msg1|1': ['1', '2', '3', '4'],
      msg2: '同源',
      msg3: '正常',
      'msg4|+1': 1,
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
