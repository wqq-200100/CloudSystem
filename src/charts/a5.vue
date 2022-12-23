<template>
  <div ref="myCharts"></div>
</template>

<script setup>
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null
const myCharts = $ref()

let data = [{
  name: "网络(个)",
  value: 12,
}, {
  name: "数据库(个)",
  value: 9,
}, {
  name: "操作系统(个)",
  value: 19,
}, {
  name: "安全产品(个)",
  value: 27,
}].reverse()

let ydata = []
for (let i = 0; i < data.length; i++) {
  ydata.push(data[i].name);
}
let datalength = []
for (let i = 0; i < data.length; i++) {
  datalength.push(0);
}
let databg = []
for (let i = 0; i < data.length; i++) {
  databg.push(data[data.length - 1].value);
}


const option = {
  grid: {
    left: '11%',
    top: '12%',
    right: '10%',
    bottom: '8%',
    containLabel: true,
  },
  xAxis: [{
    show: false,
  }],
  yAxis: [{
    axisTick: 'none',
    axisLine: 'none',
    offset: '10',
    axisLabel: {
      textStyle: {
        fontSize: 14,
        color: '#7789AA'
      }
    },
    data: ydata,
  },
    {
      axisTick: 'none',
      axisLine: 'none',
      position: 'right',
      offset: 10,
      axisLabel: {
        margin: 0,
        interval: 0,
        inside: true,
        padding: [0, 10, 6, 0],
        // color: '#4CB1A0',
        fontSize: 14,
        fontFamily: ' DIN Alternate',
        fontWeight: 'bold',
        color: '#273756',
        align: 'right',
        verticalAlign: 'bottom',
      },
      data: data
    },
    {
      axisLine: {
        lineStyle: {
          color: 'rgba(0,0,0,0)'
        }
      },
      data: [],
    }],
  series: [
    {
      name: 'series',
      type: 'bar',
      stack: 'series',
      yAxisIndex: 0,
      data: data,
      barWidth: 4,
      showBackground: '#D6E2F2',
      itemStyle: {
        normal: {
          color: {
            type: 'linear',
            x: 0,
            y: 0,
            x2: 1,
            y2: 0,
            colorStops: [
              // {
              //     offset: 0,
              //     color: '#bae7ff', // 0%
              // },
              {
                offset: 1,
                color: '#e07c66', // 100%
              },
            ],
          },
          barBorderRadius: 0,
        }
      },
      markPoint: {
        symbol: 'rect',
        symbolSize: [13, 6],
        label: {
          show: false
        },
        itemStyle: {
          color: '#00CD68'
        },
        data: data.map((v, i) => {
          return {
            value: v.value,
            xAxis: v.value,
            yAxis: i,
            itemStyle: {
              color: '#b95a4e'
            }
          }
        })
      },
      z: 2
    },
  ]
};

onMounted(() => {
  myChart = echarts.init(myCharts)
  myChart.setOption(option)
})
</script>

<style scoped lang='less'>

</style>
