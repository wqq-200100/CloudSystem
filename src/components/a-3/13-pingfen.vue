<template>
<div style="display: flex;margin-top: 80px;">
  <a7 style="width: 400px;height: 400px;" :title="title" :num="num"/>
  <a7 style="width: 400px;margin-left: 60px;height: 400px;" :title="title1" :num="num1"/>
</div>
</template>

<script setup>
import a7 from "../../charts/a7.vue";

const title = $ref('设备完整度')
const num = $ref([50, 83, 85, 85, 70])

const title1 = $ref('用户满意度')
const num1 = $ref([78, 68, 80, 89, 90])

</script>

<style scoped lang='less'>

</style>
