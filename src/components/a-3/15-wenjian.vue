<template>
<!--  <el-button type="danger">投诉</el-button>-->
  <div style="display: flex;">
    <div >
      <span style="font-weight: bold;font-size: 15px;margin-left: 10px;">故障处理人：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>
    <div style="margin-left: 30px;">
      <span style="font-weight: bold;font-size: 15px">故障名称：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>
  </div>


  <div style="display: flex;margin-left: 10px;">

    <!--  系统名下拉框-->
    <div style="margin-top: 30px;">
      <span style="font-weight: bold;font-size: 15px">故障日期：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>

    <div style="margin-top: 30px;margin-left: 30px;">
      <span style="font-weight: bold;font-size: 15px">故障类别：</span>
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

  <el-table :data="myData" style="width: 90%;margin-top: 20px;">
    <el-table-column label="云服务商" prop="name"  width="120"/>
    <el-table-column label="故障类别" prop="net" width="120" />
    <el-table-column label="故障日期" prop="time" width="130" align="center"/>
    <el-table-column label="处理人" prop="ren" width="80" />
    <el-table-column label="备注" prop="zhu" width="80" />

    <el-table-column align="center" width="180">
      <template #header>
        <el-input v-model="search" size="small" placeholder="搜索服务商" />
      </template>
      <template #default="scope">
        <el-button type="success"
        >编辑</el-button
        >
        <el-button
            type="danger"
        >删除</el-button
        >
      </template>
    </el-table-column  >
  </el-table>

  <el-button type="primary" style="width: 90px;margin-top: 20px;margin-left: 19%;">确认提交</el-button>
</template>

<script setup>
import Mock from "mockjs";
import {computed} from "vue";

const search = $ref('')

Mock.Random.extend({
  phone: function () {
    let phonePrefixs = ['132', '135', '189'] // 自己写前缀哈
    return this.pick(phonePrefixs) + Mock.mock(/\d{8}/) //Number()
  }
})

const myData = Mock.mock({
  'data|4-6': [
    {
      'name|1': ['鲲鹏云', '城运云','新华三云','浪潮云','曙光云'],
      'net|1': ['服务器宕机', '服务器卡死', '网络故障', '应用故障', ' 其他故障 '],
      'xin|1': ['是', '否'],
      'xieyi|1': ['tcp','http','https','udp'],
      time:  `${2022}-@date("MM-dd")`,
      ren:`${'张'}@cword(1,2)`,
      bei: '无',
      lian: '@cword(2,3)',
      zhu: '无',
    }
  ]

}).data
</script>

<style scoped lang='less'>

</style>
