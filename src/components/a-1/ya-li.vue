<template>
  <div class="label-title">
    压力安全测试
  </div>

  <div style="margin: 20px;">
    <div style="display: flex">
      <!--  系统名下拉框-->
      <div style="margin-top: 20px;">
        <span style="font-weight: bold;font-size: 15px">系统名称：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <!--  系统名下拉框-->
      <div style="margin-top: 20px;margin-left: 60px;">
        <span style="font-weight: bold;font-size: 15px">测试类型：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <!--  系统名下拉框-->
      <div style="margin-top: 20px;margin-left: 60px;">
        <span style="font-weight: bold;font-size: 15px">是否信创：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
    </div>
  </div>

  <div style="font-weight: bold;font-size: 15px;margin-left: 22px;margin-top: 40px;">测试记录：</div>
  <el-table :data="myData" stripe style="width: 80%;margin-top: 20px;">
    <el-table-column prop="net" label="系统名称" width="180"/>
    <el-table-column prop="yali" label="测试类型" width="180"/>
    <el-table-column prop="xin" label="是否信创" width="180"/>
    <el-table-column prop="ip" label="ip" width="180"/>
    <el-table-column prop="xieyi" label="协议"/>
    <el-table-column prop="time" label="测试时间"/>
    <el-table-column prop="duankou" label="负责人"/>
    <el-table-column prop="msg" label="联系方式"/>

    <el-table-column label="操作">
      <template #default="scope">
        <el-button size="small"
        >编辑
        </el-button
        >
        <el-button
            size="small"
            type="danger"
        >删除
        </el-button
        >
      </template>
    </el-table-column>
  </el-table>
</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|7-9': [
    {
      net: 'windows',
      ip: '@ip',
      'xieyi|1': ['HTTP', 'SSL', 'HTTPS', 'TCP', 'UDP'],
      time: '@datetime',
      msg: '@string(number,11)',
      duankou: '@cword(2,3)',
      'yali|1': ['负载测试', '压力测试', '容量测试', '可伸缩性测试'],
      'xin|1': ['是','否'],
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
