<template>
  <div class="label-title">
    进出机房
  </div>

  <div style="display: flex">
    <div style="margin-top: 50px;margin-left: 30px;">
      <span style="font-weight: bold;font-size: 15px">服务商名称：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择服务商" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>

    <div style="margin-top: 50px;margin-left: 60px;">
      <span style="font-weight: bold;font-size: 15px">机房名称：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择机房" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>

    <div class="demo-range" style="margin-top: 50px;margin-left: 60px;">
      <span style="font-weight: bold;font-size: 15px">进出时间：</span>
      <el-time-picker
          v-model="value1"
          is-range
          range-separator="To"
          start-placeholder="进入时间"
          end-placeholder="出去时间"
      />
    </div>
  </div>

  <div style="margin: 30px">
    <span style="font-weight: bold;font-size: 15px">进出原因：</span>
    <input type="text" style="height: 100px;width: 420px;">
  </div>

  <div style="font-weight: bold;font-size: 15px;margin: 30px;">设备明细：</div>
  <el-table :data="myData1" stripe style="width: 50%;margin-top: 20px;margin-left: 80px;">
    <el-table-column prop="net" label="设备类型" width="180"/>
    <el-table-column prop="ip" label="设备型号" width="180"/>
    <el-table-column prop="time" label="进出时间"/>
    <el-table-column prop="msg" label="负责人"/>
    <el-table-column prop="msg" label="备注"/>
  </el-table>

  <el-button type="primary" style="margin-left: 30%;margin-top: 10px;">提交</el-button>

</template>

<script setup>
import Mock from "mockjs";

const value = $ref('')
const options = [
  {
    value: 'Option1',
    label: 'Option1',
  }]

const value1 = $ref([
  new Date(2022, 9, 10, 0, 0),
  new Date(2022, 9, 10, 0, 0),
])

const myData1 = Mock.mock({
  'data|9-10': [
    {
      'net|1': ['计算型服务器', '存储型服务器', ' 安全设备', '网络设备'],
      'ip|1': ['云服务器_QVM_云主机', '云存储_对象存储'],
      'time|1': [
        '2022/2/13',
        '2022/4/23',
        '2022/10/30',
        '2022/4/23',
        '2022/8/28',
        '2022/9/10',
        '2022/8/13'],
      msg: '无'
    }
  ]

}).data

</script>

<style scoped lang='less'>

</style>
