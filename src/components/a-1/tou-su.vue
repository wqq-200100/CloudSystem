<template>
  <div class="label-title">
    投诉处理
  </div>

  <div style="margin-top: 30px;margin-left: 10px;" >
    <span style="font-weight: bold;font-size: 15px">服务商名称：</span>
    <el-select v-model="value" class="m-2" placeholder="请选择系统" size="large">
      <el-option
          v-for="item in options"
          :key="item.value"
          :label="item.label"
          :value="item.value"
      />
    </el-select>
    <el-button type="primary" style="margin-left: 20px;">新增</el-button>
  </div>

  <div style="font-weight: bold;font-size: 15px;margin: 30px;">投诉记录：</div>
  <el-table stripe style="width: 50%;margin-top: 20px;">
    <el-table-column prop="net" label="投诉人" width="80"  />
    <el-table-column prop="ip" label="所属单位" width="120" />
    <el-table-column prop="xieyi" label="所属系统" width="120"/>
    <el-table-column prop="time" label="投诉人电话" width="120" />
    <el-table-column prop="duankou" label="时间" width="120" />
    <el-table-column prop="msg" label="投诉内容" />
    <el-table-column prop="msg" label="操作" />

  </el-table>
</template>

<script setup>

</script>

<style scoped lang='less'>

</style>
