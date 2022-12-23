<template>
  <div class="label-title">
    其他事项工单
  </div>

  <div style="display: flex;margin-left: 10px;">
    <div style="margin-top: 30px;">
      联系人：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      联系方式：<input type="text" style="height: 25px;"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </div>
    <!--  系统名下拉框-->
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
    </div>
    <!--  系统名下拉框-->
    <div style="margin-top: 30px;margin-left: 60px;" >
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

  <div style="font-weight: bold;font-size: 15px;margin-left: 13px;margin-top: 40px;">上传附件：<button>添加</button></div>

  <el-table stripe style="width: 50%;margin-top: 20px;">
    <el-table-column prop="net" label="文件名称" width="180"  />
    <el-table-column prop="ip" label="文件类型" width="180" />
    <el-table-column prop="xieyi" label="备注" />
    <el-table-column prop="time" label="上传时间" />
    <el-table-column prop="duankou" label="操作" />

  </el-table>

</template>

<script setup>

</script>

<style scoped lang='less'>

</style>
