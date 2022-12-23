<template>
  <div ref="myCharts" ></div>
</template>

<script setup>
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null
const myCharts = $ref()
const props = defineProps({
  num:[],
  title:''
})

let xaxisData = ["新华云", "浪潮云", "曙光云", "华为云", "阿里云"];
let yaxisData = props.num;

const option = {
  title: {
    text:props.title,
    x: 'center',
  },
  tooltip: {
    trigger: "axis",
    axisPointer: {
      type: "shadow",
    },
    backgroundColor: "rgba(255,255,255,0.75)",
    extraCssText: "box-shadow: 2px 2px 4px 0px rgba(0,0,0,0.3);",
    textStyle: {
      fontSize: 14,
      color: "#000",
    },
    formatter: (params) => {
      const item = params[0];
      return item.name + " : " + item.value + "%";
    },
  },
  grid: {
    left: "1%",
    right: "0%",
    top: "20%",
    bottom: "1%",
    containLabel: true,
  },
  xAxis: [
    {
      type: "category",
      axisLabel: {
        interval: 0,
        color: "#030202",
        fontSize: 14,
      },
      axisLine: {
        lineStyle: {
          //y轴网格线设置
          color: "#545454",
          width: 1,
        },
      },
      axisTick: {
        show: false,
      },
      data: xaxisData,
    },
  ],
  yAxis: [
    {
      type: "value",
      name: "%",
      nameTextStyle: {
        color: "#070707",
        fontWeight: 400,
        fontSize: 14,
      },
      axisTick: {
        show: false,
      },
      axisLine: {
        show: true,
        lineStyle: {
          color: "#030303",
          width: 1,
        },
      },
      splitLine: {
        show: false,
      },
      axisLabel: {
        show: true,
        fontSize: 14,
        color: "#020202",
      },
    },
  ],
  series: [
    {
      type: "bar",
      barWidth: 16,
      label: {
        show: true,
        position: "top",
        color: "#007AFF",
      },
      itemStyle: {
        borderRadius: [8, 8, 0, 0],
        color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
          {
            offset: 0,
            color: "#007AFF",
          },
          {
            offset: 1,
            color: "rgba(0, 122, 255, 0)",
          },
        ]),
      },
      data: yaxisData,
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
