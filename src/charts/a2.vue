<template>
  <div ref="myCharts"></div>
</template>

<script setup>
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null
const myCharts = $ref()
const props= defineProps({
  title:[],
  num:[],
  sum:[]
})

const option = {
  backgroundColor: '#fff',
  grid: {
    containLabel: true,
    left: 20,
    right: 20,
    bottom: 10,
    top: 40,
  },
  xAxis: {
    axisLabel: {
      color: '#c0c3cd',
      fontSize: 14,
      interval: 0,
    },
    axisTick: {
      show: false,
    },
    splitLine: {
      show: false,
    },
    axisLine: {
      show: false,
    },
    data: props.title,
    type: 'category',
  },
  yAxis: {
    axisLabel: {
      color: '#c0c3cd',
      fontSize: 14,
    },
    axisTick: {
      show: false,
    },
    splitLine: {
      show: false,
    },
    axisLine: {
      show: false,
    },
    name: '',
  },
  series: [
    {
      data:props.num,
      type: 'bar',
      barMaxWidth: 'auto',
      barWidth: 30,
      itemStyle: {
        color: '#6dcdea',
      },
      label: {
        show: true,
        position: 'top',
        // distance: 10,
        // color: '#fff'
      },
    },
    {
      data: props.sum,
      type: 'bar',
      barMaxWidth: 'auto',
      barWidth: 30,
      barGap: '-100%',
      zlevel: -1,
      itemStyle: {
        color: '#d0d9da',
      },
    },
  ],
};


onMounted(() => {
  myChart = echarts.init(myCharts)
  myChart.setOption(option)
})
</script>

<style scoped lang='less'>

</style>
