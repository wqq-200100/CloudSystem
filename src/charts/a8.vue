<template>
  <div ref="myCharts" ></div>
</template>

<script setup>
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null
const myCharts = $ref()
var loadData = [];
var titleArr = ["新华云", "浪潮云", "曙光云", "华为云", "阿里云"];
var allArr = [22, 18, 21, 17, 12];
var chuqinArr = [12, 8, 11, 13, 17];

const option = {
  tooltip: {
    trigger: 'axis',
    axisPointer: {
      type: 'shadow'
    }
  },
  legend: {
    top: '10%',
    data: ['新建连接数', '关闭连接数'],
    textStyle: {
      //字体颜色
      color: '#070707',
      fontSize: 16
    }
  },
  grid: {
    top: '20%',
    left: '10%',
    right: '10%',
    bottom: '15%',
    containLabel: true
  },
  yAxis: {
    type: 'value',

    splitLine: {
      show: true,
      lineStyle: {
        color: '#1a4b98',
        type: 'solid'
      }
    },
    axisLine: {
      show: true,
      lineStyle: {
        color: '#009dff'
      }
    },
    axisTick: {
      show: false
    },
    axisLabel: {
      color: '#0a0a0a'
    }
  },
  xAxis: {
    type: 'category',
    data: titleArr,
    axisLine: {
      show: true,
      lineStyle: {
        color: '#009dff'
      }
    },
    axisTick: {
      show: false
    },
    axisLabel: {
      color: '#070707', //x轴字体颜色
      textStyle: {
        fontSize: 16
      },
      formatter: function (params) {
        var newParamsName = "";// 最终拼接成的字符串
        var paramsNameNumber = params.length;// 实际标签的个数
        var provideNumber = 4;// 每行能显示的字的个数
        var rowNumber = Math.ceil(paramsNameNumber / provideNumber);// 换行的话，需要显示几行，向上取整
        /**
         * 判断标签的个数是否大于规定的个数， 如果大于，则进行换行处理 如果不大于，即等于或小于，就返回原标签
         */
        // 条件等同于rowNumber>1
        if (paramsNameNumber > provideNumber) {
          /** 循环每一行,p表示行 */
          for (var p = 0; p < rowNumber; p++) {
            var tempStr = "";// 表示每一次截取的字符串
            var start = p * provideNumber;// 开始截取的位置
            var end = start + provideNumber;// 结束截取的位置
            // 此处特殊处理最后一行的索引值
            if (p == rowNumber - 1) {
              // 最后一次不换行
              tempStr = params.substring(start, paramsNameNumber);
            } else {
              // 每一次拼接字符串并换行
              tempStr = params.substring(start, end) + "\n";
            }
            newParamsName += tempStr;// 最终拼成的字符串
          }

        } else {
          // 将旧标签的值赋给新标签
          newParamsName = params;
        }
        //将最终的字符串返回
        return newParamsName
      }
    }
  },
  series: [
    {
      name: '新建连接数',
      type: 'bar',
      barWidth: 12,
      barGap: '80%',
      data: allArr,
      itemStyle: {
        color: {
          type: 'linear',
          x: 0,
          y: 1,
          x2: 0,
          y2: 0,
          colorStops: [
            {
              offset: 0,
              color: '#8BDCFF' // 0% 处的颜色
            },
            {
              offset: 1,
              color: '#4594E8' // 100% 处的颜色
            }
          ],
          global: false // 缺省为 false
        },
        normal: {
          //柱形图上方标题
          label: {
            show: true,
            position: 'top',
            textStyle: {
              color: '#1b7be7',
              fontSize: 12
            }
          },
          barBorderRadius: [24, 24, 0, 0],
          color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [ //颜色渐变
            {
              offset: 0,
              color: '#00b1f2'
            },
            {
              offset: 0.5,
              color: '#00b1f2'
            },
            {
              offset: 1,
              color: '#00b1f2'
            }
          ])
        }
      }
    },
    {
      name: '关闭连接数',
      type: 'bar',
      barWidth: 12,
      barGap: '80%',
      data: chuqinArr,
      itemStyle: {
        color: {
          type: 'linear',
          x: 0,
          y: 1,
          x2: 0,
          y2: 0,
          colorStops: [
            {
              offset: 0,
              color: '#8BDCFF' // 0% 处的颜色
            },
            {
              offset: 1,
              color: '#4594E8' // 100% 处的颜色
            }
          ],
          global: false // 缺省为 false
        },
        normal: {
          //柱形图上方标题
          label: {
            show: true,
            position: 'top',
            textStyle: {
              color: '#95ea2b',
              fontSize: 12
            }
          },
          barBorderRadius: [24, 24, 0, 0],
          color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [ //颜色渐变
            {
              offset: 0,
              color: '#7def86'
            },
            {
              offset: 0.5,
              color: '#7def86'
            },
            {
              offset: 1,
              color: '#7def86'
            }
          ])
        }
      }
    }
  ]
};


onMounted(() => {
  myChart = echarts.init(myCharts)
  myChart.setOption(option)
})
</script>

<style scoped lang='less'>

</style>
