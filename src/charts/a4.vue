<template>
  <div ref="myCharts"></div>
</template>

<script setup>
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null
const myCharts = $ref()


const colors = [{
  type: "linear",
  x: 1,
  y: 0,
  x2: 0,
  y2: 0,
  colorStops: [{
    offset: 0,
    color: "#8331D9"
  },
    {
      offset: 0.5,
      color: "#720DFF"
    },
    {
      offset: 0.5,
      color: "#B635FC"
    },
    {
      offset: 1,
      color: "#7F2CF1"
    }
  ]
},
  {
    type: "linear",
    x: 1,
    y: 0,
    x2: 0,
    y2: 0,
    colorStops: [{
      offset: 0,
      color: "#8d7cc0"
    },
      {
        offset: 0.5,
        color: "#977bec"
      },
      {
        offset: 0.5,
        color: "#b7a1e1"
      },
      {
        offset: 1,
        color: "#a463f3"
      }
    ]
  },
  {
    type: "linear",
    x: 1,
    y: 0,
    x2: 0,
    y2: 0,
    colorStops: [{
      offset: 0,
      color: "#65fccf"
    },
      {
        offset: 0.5,
        color: "#63dab7"
      },
      {
        offset: 0.5,
        color: "#8eeadc"
      },
      {
        offset: 1,
        color: "#83ccbb"
      }
    ]
  },
  {
    type: "linear",
    x: 1,
    y: 0,
    x2: 0,
    y2: 0,
    colorStops: [{
      offset: 0,
      color: "#289DF5"
    },
      {
        offset: 0.5,
        color: "#0DE8FF"
      },
      {
        offset: 0.5,
        color: "#49B1FB"
      },
      {
        offset: 1,
        color: "#17E9FD"
      }
    ]
  }
];
const barWidth = 30;

const option = {
  title: {
    text: '存储数据',
    x: 'center',
  },
  tooltip: {
    trigger: "item"
  },
  grid: {
    left: 80,
    right: 40,
    bottom: 100,
    top: 100,
    containLabel: true
  },
  xAxis: {
    data: ["集中式存储", "分布式存储"],
    axisTick: {
      show: true
    },
    axisLine: {
      lineStyle: {
        color: 'rgba(151, 151, 151, 0.3)'
      }
    },
    axisLabel: {
      color: '#000',
      fontSize: 12,
      padding:15
    }
  },
  yAxis: {
    type: 'value',
    name: '（TB）',
    nameTextStyle: {
      color: "#000",
      fontSize: 12,
      padding: [5, 0,20, -50],
    },
    axisLine: {
      show: true,
      lineStyle: {
        color: 'rgba(151, 151, 151, 0.3)',
      }
    },
    splitLine: {
      show: true,
      lineStyle: {
        color: 'rgba(151, 151, 151, 0.1)',
      },
    },
    axisLabel: {
      show: true,
      textStyle: {
        color: '#000',
      },
      padding:10
    },
  },
  series: [{
    z: 1,
    type: "bar",
    barWidth: barWidth,
    label: {
      normal: {
        show: true,
        position: "top",
        formatter: function(data) {
          return '{a'+data.dataIndex+'|' + data.value + '}';

        },
        rich: {
          a0: {
            color: 'rgb(128,106,231)',
            fontSize: 16,
            fontFamily: 'DIN',
            fontWeight: 'bold'
          },
          a1: {
            color: '#35eede',
            fontSize: 16,
            fontFamily: 'DIN',
            fontWeight: 'bold'
          },
          a2: {
            color: '#b01b3e',
            fontSize: 16,
            fontFamily: 'DIN',
            fontWeight: 'bold'
          }
        }
      },
    },
    data: [{
      value: 42,
      itemStyle: {
        normal: {
          color: colors[1]
        }
      }
    },
      {
        value: 60,
        itemStyle: {
          normal: {
            color: colors[2]
          }
        }
      },
    ]
  },
    {
      z: 2,
      name: "底部",
      type: "pictorialBar",
      data: [{
        value: 1,
        itemStyle: {
          normal: {
            color: colors[1]
          }
        }
      },
        {
          value: 1,
          itemStyle: {
            normal: {
              color: colors[2]
            }
          }
        },
        {
          value: 1,
          itemStyle: {
            normal: {
              color: colors[3]
            }
          }
        },
      ],
      symbol: "diamond",
      symbolOffset: [0, "50%"],
      symbolSize: [barWidth, 10]
    },
    {
      z: 3,
      name: "上部1",
      type: "pictorialBar",
      symbolPosition: "end",
      data: [{
        value: 0,
        itemStyle: {
          normal: {
            borderColor: colors[1],
            borderWidth: 2,
            color: colors[1]
          }
        }
      },
        {
          value: 0,
          itemStyle: {
            normal: {
              borderColor: colors[2],
              borderWidth: 2,
              color: colors[2]
            }
          }
        },
      ],
      symbol: "diamond",
      symbolOffset: [0, "-50%"],
      symbolSize: [barWidth - 4, (10 * (barWidth - 4)) / barWidth]
    }
  ]
}


onMounted(() => {
  myChart = echarts.init(myCharts)
  myChart.setOption(option)
})
</script>

<style scoped lang='less'>

</style>
