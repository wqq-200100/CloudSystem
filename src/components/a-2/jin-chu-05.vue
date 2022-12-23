<template>
  <div class="title_b">
    进出机房
  </div>

  <!--  系统名下拉框-->
  <div style="margin-top: 30px;margin-left: 10px;">
    <div style="margin-top: 30px;">
      姓名：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      联系方式：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;
    </div>

    <div style="margin-top: 40px;">
      <sapn>机房名称：</sapn>
      <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
      <span style="margin-left: 30px;">进出时间：</span>
      <el-time-picker
          v-model="value1"
          is-range
          range-separator="To"
          start-placeholder="进入时间"
          end-placeholder="出去时间"
      />
    </div>

   <div style="display: flex;align-items: center;margin-top: 50px;">
     <div>进出原因：</div>
     <el-input
         v-model="textarea"
         :rows="2"
         type="textarea"
         placeholder="请输入进出原因"
         style="width: 400px;"
     />
   </div>
   </div>

  <div style="margin-left: 10px;margin-top: 50px;">
    <div>进出明细：</div>
    <el-table
        :data="myData"
        :row-class-name="tableRowClassName"
        style="width: 100%;margin-top: 20px;"
    >
      <el-table-column prop="net" label="姓名" width="100"/>
      <el-table-column prop="phone" label="联系电话" width="130"/>
      <el-table-column prop="ip" label="身份证号码" width="190"/>
      <el-table-column prop="liyou" label="访问理由" width="100">
        <template #default="scope">
          <el-button size="small">预览</el-button>
        </template>

      </el-table-column>
      <el-table-column prop="time" label="访问时间" width="180"/>
      <el-table-column prop="bei" label="备注" width="120"/>

      <el-table-column label="操作" width="180">
        <template #default="scope">
          <el-button size="small">修改
          </el-button>
          <el-button
              size="small"
              type="danger">删除
          </el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>

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
  'data|5-8': [
    {
      'net|1': `${'李'}@cword(1,2)`,
      ip: '@id',
      'xieyi|1': ['TCP', 'HTTPS','HTTP'],
      time: '@datetime',
      bei: '无',
      phone:['@phone'],
      liyou:'@cword(7,10)'
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

const textarea = $ref('')
</script>

<style scoped lang='less'>

</style>
