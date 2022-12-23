<template>
  <div class="title_b">
    文件管理
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;display: flex;align-items: center;flex-wrap: wrap;width: 1200px;height: 120px;">
      <div>
        <span style="font-size: 16px;margin-left: 25px;">云服务商：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择服务商" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <div >
        <span style="font-size: 16px;margin-left: 25px;">故障名称：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择服务商" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <div >
        <span style="font-size: 16px;margin-left: 25px;">故障类别：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择服务商" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <div >
        <span style="font-size: 16px;margin-left: 25px;">故障日期：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择服务商" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <div >
        <span style="font-size: 16px;margin-left: 25px;">故障处理人：</span>
        <el-select v-model="value" class="m-2" placeholder="请选择服务商" size="large">
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </div>
      <el-button type="success"  style="margin-left: 20px;">新增</el-button>
    </div>
  </div>


  <div style="display: flex;align-items: center;margin-top: 30px;margin-left: 30px;">
    <div>上传附件：</div>
    <el-button plain style="margin-left: 20px;">上传附件</el-button>
  </div>

  <el-table
      :data="myData"
      :row-class-name="tableRowClassName"
      style="width: 50%;margin-top: 20px;margin-left: 60px;"
  >
    <el-table-column prop="name" label="云服务商" width="120"/>
    <el-table-column prop="xieyi" label="故障名称" width="130"/>
    <el-table-column prop="zhu" label="故障类别" width="120"/>
    <el-table-column prop="zhu" label="故障日期" width="120"/>
    <el-table-column prop="zhu" label="故障处理人" width="120"/>
    <el-table-column prop="zhu" label="文件" width="120"/>

    <el-table-column label="操作" width="180">
      <template #default="scope">
        <el-button round>操作</el-button>
        <el-button type="danger" round>删除</el-button>
      </template>
    </el-table-column>
  </el-table>

  <el-button type="primary" style="margin-left: 25%;margin-top: 10px;width: 90px;">提交</el-button>

</template>

<script setup>
import Mock from "mockjs";

const input = $ref('')

Mock.Random.extend({
  phone: function () {
    let phonePrefixs = ['132', '135', '189'] // 自己写前缀哈
    return this.pick(phonePrefixs) + Mock.mock(/\d{8}/) //Number()
  }
})

const myData = $ref('')

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
