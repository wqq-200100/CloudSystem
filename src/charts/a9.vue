<template>
  <div ref="myCharts" ></div>
</template>

<script setup>
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null
const myCharts = $ref()

let result = {
  total: 278,
  value: 218,
  color: '#01EAFF'
}
result.rate = result.value/result.total.toFixed(4);
console.log(result.rate*360)
let echartData = [
  {
    name: '数量',
    value: result.value,
    itemStyle: {
      normal: {
        color: result.color,
      },
    },
  },
  {
    name: '剩下',
    value: (result.total - result.value),
    itemStyle: {
      normal: {
        color: 'rgba(31, 110, 255, 0)',
      },
    },
  },
];
let echartData2 = [
  {
    name: '数量',
    value: (result.total - result.value),
    itemStyle: {
      normal: {
        color: 'rgba(31, 110, 255, .4)',
      },
    },
  },
  {
    name: '剩下',
    value: result.value,
    itemStyle: {
      normal: {
        color: 'rgba(31, 110, 255, 0)',
      },
    },
  },
];
const option = {
  title: [
    {
      text: '异常连接',
      x: 'center',
      top: '50%',
      textStyle: {
        color: '#731b1b',
        fontSize: 20,
        fontWeight: '500',
      },
    },
    {
      text: '23.99%',
      x: 'center',
      top: '42%',
      textStyle: {
        fontSize: 30  ,
        color: '#18c8d2',
        foontWeight: '500',
      },
    },
  ],
  polar: {
    radius: ['44%', '50%'],
    center: ['50%', '50%'],
  },
  angleAxis: {
    max: 100,
    show: false,
  },
  radiusAxis: {
    type: 'category',
    show: true,
    axisLabel: {
      show: false,
    },
    axisLine: {
      show: false,
    },
    axisTick: {
      show: false,
    },
  },
  series: [
    {
      type: 'pie',
      startAngle:90,
      radius: ['60%', '80%'],
      center: ['50%', '50%'],
      data: echartData,
      hoverAnimation: false,
      label: {
        show: false,
      },
    },
    {
      type: 'pie',
      startAngle: (90 + (1-result.rate)*360),
      radius: ['62%', '77%'],
      center: ['50%', '50%'],
      data: echartData2,
      hoverAnimation: false,
      label: {
        show: false,
      },
    },
    {
      name: '',
      type: 'pie',
      startAngle: 90,
      radius: '45%',
      animation:false,
      hoverAnimation: false,
      center: ['50%', '50%'],
      itemStyle: {
        normal: {
          labelLine: {
            show: false,
          },
          color: new echarts.graphic.RadialGradient(0.5, 0.5, 1, [
            {
              offset: 1,
              color: 'rgba(50,171,241, 1)',
            },
            {
              offset: 0,
              color: 'rgba(55,70,130, 0)',
            },
          ]),
          shadowBlur: 10,
        },
      },
      data: [
        {
          value: 100,
        },
      ],
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
