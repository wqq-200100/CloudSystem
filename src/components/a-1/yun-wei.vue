<template>
  <div class="label-title">
    文件管理
  </div>

  <!--  <div style="margin: 20px;">
      <div style="margin-top: 10px;display: flex">
        <input type="text" placeholder="请输入关键字" style="border-radius: 8px;border: 1px solid #999;">
        <button style="background: #3eb2fa;border: none;border-radius: 8px;width: 70px;height: 30px;margin:1px 10px;">搜索</button>
        <button style="background: #d4d7d9;border: none;border-radius: 8px;width: 70px;height: 30px;margin:1px 10px;">重置</button>
        <button style="background: #86b3fd;border: none;border-radius: 8px;width: 70px;height: 30px;margin:1px 10px;">上传附件</button>
      </div>
    </div>-->

  <div style="display: flex;">
    <div style="margin-top: 30px;margin-left: 20px;">
      <span style="font-weight: bold;font-size: 15px">云服务商：</span>
      <el-select v-model="value" class="m-2" placeholder="请选择" size="large">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
      </el-select>
    </div>
    <div style="margin-top: 30px;margin-left: 60px;">
      <span style="font-weight: bold;font-size: 15px">故障处理人：</span>
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


  <div style="display: flex;margin-left: 10px;">
    <div style="margin-top: 30px;margin-left: 10px;">
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
    <!--  系统名下拉框-->
    <div style="margin-top: 30px;margin-left: 60px;">
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

    <div style="margin-top: 30px;margin-left: 60px;">
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


  <!--  <el-table stripe style="width: 50%;margin-top: 20px;">
      <el-table-column prop="net" label="文件名称" width="180"  />
      <el-table-column prop="ip" label="文件类型" width="180" />
      <el-table-column prop="xieyi" label="备注" />
      <el-table-column prop="time" label="上传时间" />
      <el-table-column prop="duankou" label="操作" />

    </el-table>-->
  <el-table :data="myData" stripe style="width: 50%;margin-top: 20px;">
    <el-table-column prop="net" label="故障名称" width="120"/>
    <el-table-column prop='ip' label="故障日期" width="120"/>
    <el-table-column prop="xieyi" label="云服务商" width="120"/>
    <el-table-column prop="ren" label="故障处理人" width="120"/>
    <el-table-column prop="bei" label="备注" width="120"/>
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
  <el-button type="primary" style="margin-left: 20%;margin-top: 15px;">提交</el-button>


</template>

<script setup>
import Mock from "mockjs";

const myData = Mock.mock({
  'data|7': [
    {
      'net|1': ['服务器宕机', '服务器卡死', '网络故障', '应用故障', ' 其他故障 '],
      'ip|1': [
        '2022/2/13',
        '2022/4/23',
        '2022/10/30',
        '2022/4/23',
        '2022/8/28',
        '2022/9/10',
        '2022/8/13'],
      'xieyi|1': ['浪潮云', '鲲鹏云'],
      'time|1': ['服务器宕机', '服务器卡死', '网络故障', '应用故障', ' 其他故障 '],
      msg: '@string(number,11)',
      duankou: '@cword(2,3)',
      'ren|1': ['管理员', '用户'],
      bei:'无'
    }
  ]
}).data

</script>

<style scoped lang='less'>

</style>
