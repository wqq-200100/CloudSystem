<template>
  <div class="myBox">

    <div style="width: 480px;background: #fff;height: 200px;display: flex;justify-content: space-between;margin:0 40px">
        <div style="display: flex;flex-direction: column;align-items: center">
          <div>120</div>
          <div>hi off从</div>
        </div>
        <div style="display: flex;flex-direction: column;align-items: center">
          <div>1.2%</div>
          <div>hi回去</div>
        </div>
        <div style="display: flex;flex-direction: column;align-items: center">
          <div>21</div>
          <div>旗舰店</div>
        </div>
      </div>

    <div style="display: flex;background: #fff;height: 40px;line-height: 40px;margin: 20px;border-radius: 4px"  >
      <div style="margin-left: 40px;">品牌：<input type="text" placeholder="请选择" style="border: 1px solid #999;height: 20px;"></div>
      <div style="margin-left: 20px;"> 主机ID：<input type="text" placeholder="全部" style="border: 1px solid #999;height: 20px;"></div>
      <div style="margin-left: 20px;">发生事件：<input type="text" placeholder="请选择" style="border: 1px solid #999;height: 20px;"></div>
      <div style="margin-left: 20px;">
        <span>进出时间：</span>
        <el-date-picker
            type="dates"
            v-model="value4"
            placeholder="选择一个或多个日期">
        </el-date-picker>
      </div>
      <div>
        <el-button type="primary" style="margin-left: 20px;">搜索</el-button>
        <el-button>重置</el-button>
      </div>
    </div>

    <div>
      <el-table :data="myData1" stripe style="width: 100%;margin-top: 20px;">
        <el-table-column prop="net" label="主机ID" width="380" align="center"/>
        <el-table-column prop="ip" label="ip地址" width="160" align="center"/>
        <el-table-column prop="time" label="品牌" align="center" width="80"/>
        <el-table-column prop="cpu" label="cpu" align="center" width="80"/>
        <el-table-column prop="nei" label="内存（条）" align="center" width="100"/>
        <el-table-column prop="yin" label="硬盘（块）" align="center" width="100"/>
        <el-table-column prop="dian" label="电源" align="center" width="80"/>
        <el-table-column prop="feng" label="风扇" align="center" width="80"/>
        <el-table-column prop="shi" label="实时事件" align="center" width="80"/>
      </el-table>
    </div>
  </div>
</template>

<script setup>
import Mock from "mockjs";

const value = $ref('')
const value4 = $ref('')
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
      'net|1':['325efOba-cdca-ded2-9a27-7b0f4db5fea5','a690e743-0415-4b70-b2b4-7e15ad52159c','27fd0c12-c28a-4322-8d1a-15ecb3180252','0c3cb114-e6ba-4709-bd63-781c9e69b609'],
      ip:'@ip',
      'time|1':['曙光','浪潮','华硕'],
      cpu:2,
      nei:6,
      yin:6,
      dian:2,
      feng:4,
      shi:'无'
    }
  ]

}).data

</script>

<style scoped lang='less'>
.myBox{
  background: #dddee0;
}
</style>
