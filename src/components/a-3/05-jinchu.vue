<template>
    <!--  系统名下拉框-->
    <div>
      <span>系统名称：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>
  <div style="margin-top: 20px;">
    进出时间:&nbsp; <el-time-picker
      v-model="value1"
      is-range
      range-separator="To"
      start-placeholder="进入时间"
      end-placeholder="出去时间"/>
    <div style="margin-top: 20px;">原因：<el-button type="info" plain >上传</el-button></div>
  </div>

  <el-table :data="myData" style="width: 70%;margin-top: 20px;">
    <el-table-column prop="lian" label="业务部门" width="120"/>
    <el-table-column prop="name" label="云服务商" width="120"/>
    <el-table-column prop="xin" label="机房位置" width="80"/>
    <el-table-column prop="time" label="进出时间" width="180" align="center"/>
    <el-table-column label="进出原因" width="120">
      <template #default="scope">
        <el-button type="info" plain>预览</el-button>
      </template>
    </el-table-column>

    <el-table-column label="操作" width="180" align="center">
      <template #default="scope">
        <el-button type="success" >编辑</el-button>
        <el-button type="danger" >删除</el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 20%;">确认提交</el-button>
</template>

<script setup>
import Mock from "mockjs";
import {computed} from "vue";

const search = $ref('')
const filterTableData = computed(() =>
    myData.filter(
        (data) => !search || data.name.toLowerCase().includes(search.toLowerCase())
    )
)

const myData = Mock.mock({
  'data|7-10': [
    {
      'name|1': ['鲲鹏云', '城运云'],
      net: '@ip',
      'xin|1': ['鲲鹏407', '城运307'],
      'xieyi|1': ['tcp', 'http', 'https', 'udp'],
      time:  `${2022}-@date("MM-dd")`,
      bei: '无',
      'lian|1':['市大数据中心',' 市卫健委','市场监管局','市住建局'],
      zhu: '无'
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
