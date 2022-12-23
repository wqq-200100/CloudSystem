<template>
  <div class="label-title">
    考评反馈
  </div>


  <div style="margin-top: 20px;margin-left: 200px;">用户满意排行</div>
  <a2 :title="title1" :num='num2' :sum="sum"  style="height: 200px;width: 25%;"/>

  <div style="margin-top: 20px;margin-left: 200px;">投诉排行</div>
  <a2 :title="title1" :num='num3' :sum="sum2"  style="height: 200px;width: 25%;"/>

</template>

<script setup>
import a2 from "../../charts/a2.vue";

const title1 = $ref(['新华云', '浪潮云', '曙光云', '华为云', '阿里云'])
const num2 = $ref( [66, 87, 68, 81, 90])
const sum = $ref([100, 100, 100, 100, 100])

const num3 = $ref([7, 2, 4, 6, 4])
const sum2 = $ref([15, 15, 15, 15, 15])
</script>

<style scoped lang='less'>

</style>
