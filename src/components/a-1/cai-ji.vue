<template>
  <div class="label-title">
    数据采集
  </div>

  <div
      style="width: 500px;display: flex;justify-content: space-between;margin-top: 20px;margin-left: 40px;font-weight: 700;font-size: 16px">
    <div>
      <div>云服务器</div>
    </div>
    <div>高性能服务器</div>
    <div>存储</div>
  </div>
  <div style="display: flex">
    <a1 :num="num"/>
    <a1 :num="num1" style="margin-left: 65px"/>
  </div>
  <a2 :title="title1" :num='num2' :sum="sum"  style="height: 300px;width: 50%;"/>

  <button style="background: #61b1e3;border: none;border-radius: 8px;width: 90px;height: 30px;margin: 40px 20px;">查看详情</button>
</template>

<script setup>
import a1 from "../../charts/a1.vue";
import a2 from "../../charts/a2.vue";

const num = $ref('1台')
const num1 = $ref('23台')

const title1 = $ref(['网络地址', '数据库', '操作系统', '防火墙', '入侵防御', '流量审计','警告事件'])
const num2 = $ref( [10, 21, 31, 12, 22, 49,0])
const sum = $ref([70, 70, 70, 70, 70, 70, 70])

</script>

<style scoped lang='less'>

</style>
