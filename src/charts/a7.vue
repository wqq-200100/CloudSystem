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
const data = ["新华云", "浪潮云", "曙光云", "华为云", "阿里云"]
const valueArr = props.num
const option = {
  title:{
    text: props.title,
    x:'center'
  },
  textStyle: {
    color: '#030303'
  },
  tooltip: {
    show: true,
    padding: 15,
    trigger: 'axis',
    axisPointer: {
      type: 'shadow'
    },
    formatter(params) {
      const item = params[0];
      return `设备完整度${item.value}% `;
    },
    extraCssText: 'width:88px;height:46px;'
  },
  grid: {
    left: '3%',
    right: '4%',
    bottom: '3%',
    top: '3%',
    containLabel: true
  },
  xAxis: {
    type: 'value',
    max: 100,
    nameGap: 2,
    nameLocation: 'end',
    // 坐标轴单位位置偏移
    nameTextStyle: {
      padding: [0, 0, 100, -10],
      top: '2%'
    },
    show: true,
    // 不显示轴线
    axisLine: {
      show: true
    },
    // 不显示刻度线
    axisTick: {
      show: false
    },
    splitLine: {// 网格线为虚线
      show: false,
      lineStyle: {
        type: 'dashed',
        color: 'rgba(108,128,151,0.3)'
      }

    },
    axisLabel: {
      formatter: '{value}%'
    }
  },
  yAxis: [
    {
      type: 'category',
      inverse: true,
      splitLine: {
        show: false
      },
      axisTick: {
        show: false
      },
      axisLine: {
        show: true,
        lineStyle: {
          color: '#6C8097'
        }
      },
      axisLabel: {
        interval: 0,
        color: '#030303',
        formatter: function(value) {
          var ret = '';
          var maxLength = 5; // 换行字数
          var valLength = value.length;
          var rowN = Math.ceil(valLength / maxLength);
          if (rowN > 1) {
            for (var i = 0; i < rowN; i++) {
              var temp = '';
              var start = i * maxLength;
              var end = start + maxLength;
              temp = value.substring(start, end) + '\n';
              ret += temp;
            }
            return ret;
          } else {
            return value;
          }
        }
      },
      data: data
    }
  ],
  series: [
    {
      type: 'bar',
      barWidth: 10,
      zlevel: 2,
      barGap: '-150%',
      itemStyle: {
        normal: {
          color: function (params) {
            //   var colorList = [
            //       ['rgba(26,255,255,0.1)', '#1AFFFF'],
            //       ['rgba(26,255,255,0.1)', '#1AFFFF'],
            //       ['rgba(108,128,151,0.1)', '#2194FF'],
            //       ['rgba(108,128,151,0.1)', '#2194FF']
            //   ];

            //   var colorItem = colorList[params.dataIndex];

            return new echarts.graphic.LinearGradient(0, 0, 1.2, 0, [{
              offset: 0,
              color: 'rgba(26,255,255,0.1)'
            },
              {
                offset: 0,
                color: '#29a63e'
              }
            ], false);
          }
        }
      },
      data: valueArr
    }
    // 背景
    // {
    //     type: 'bar',
    //     barWidth: 22,
    //     itemStyle: {
    //         normal: {
    //             color: 'rgba(108,128,151,0.1)',
    //         },
    //     },
    //       data: [100, 100, 100,100],
    // },
  ]
};


onMounted(() => {
  myChart = echarts.init(myCharts)
  myChart.setOption(option)
})
</script>

<style scoped lang='less'>

</style>
