<template>
  <div ref="myCharts"></div>
</template>

<script setup>
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null
const myCharts = $ref()

let dataList = [{
  name: '1月',
  value: '62'
}, {
  name: '2月',
  value: '76.5'
}, {
  name: '3月',
  value: '85.3'
}, {
  name: '4月',
  value: '66'
}, {
  name: '5月',
  value: '85.2'
},
  {
  name: '6月',
  value: '85.8'
},
  {
  name: '7月',
  value: '5.8'
},{
  name: '8月',
  value: '65.8'
},{
  name: '9月',
  value: '85.8'
},{
  name: '10月',
  value: '75.8'
},{
  name: '11月',
  value: '85.8'
},{
  name: '12月',
  value: '75.8'
},
]


const option = {
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(17,95,182,0.5)',
    textStyle: {
      color: "#fff"
    },
    triggerOn: "mousemove",
    showContent: true,
  },
  title: {
    text: '流日志数据',
    x: 'center',
    // left: 26,
    // top: 26,
    textStyle: {
      color: '#0a0101',
      fontSize: 22,
      fontWeight: 50000,
      fontFamily: 'PingFang SC'
    }
  },
  grid: {
    left: '10%',
    right: '10%',
    bottom: '20%',
    top: '28%',
    containLabel: true
  },
  dataZoom: [{
    type: 'inside',
    start: 0,
    end: dataList.length > 15 ? 35 : 100
  }],
  xAxis: {
    axisLine: {
      lineStyle: {
        color: '#000305'
      }
    },
    splitLine: {
      show: false,
    },
    axisTick: {
      show: false
    },
    //轴线上的字
    axisLabel: {
      show: true,
      textStyle: {
        color: 'rgba(12,0,0,0.8)',
        fontSize: '14'
      }
    },
    data: ['1月', '2月', '3月', '4月', '5月', '6月' ,'7月' ,'8月','9月','10月','11月','12月']
  },
  yAxis: [{
    nameTextStyle: {
      color: 'rgba(12,2,2,0.8)'
    },
    type: 'value',
    splitNumber: 4,
    axisTick: {
      show: false
    },
    //轴线上的字
    axisLabel: {
      show: true,
      textStyle: {
        fontSize: '14',
        color: 'rgba(9,1,1,0.8)'
      }
    },
    axisLine: {
      lineStyle: {
        color: '#000102'
      }
    },
    //网格线
    splitLine: {
      show: false,
      lineStyle: {
        color: '#0a0b0e'
      }
    }
  }],
  series: [{
    name: '脐橙',
    type: 'line',
    smooth: true, //是否平滑曲线显示
    showSymbol: false,
    markPoint: {
      data: [{
        name: '周最高',
        value: 320,
        xAxis: 4,
        yAxis: 320
      }]
    },
    itemStyle: {
      color: '#F3A22D',
      borderColor: '#F3A22D',
      borderWidth: 1
    },
    lineStyle: {
      normal: {
        width: 2,
        color: {
          type: 'linear',
          colorStops: [{
            offset: 0,
            color: '#F3A22D' // 0% 处的颜色
          },
            {
              offset: 1,
              color: '#F3A22D' // 100% 处的颜色
            }
          ],
          globalCoord: false // 缺省为 false
        },
        shadowColor: '#F3A22D',
        shadowBlur: 30,
        shadowOffsetY: 5
      }
    },
    areaStyle: {
      //区域填充样式
      normal: {
        color: new echarts.graphic.LinearGradient(
            0,
            0,
            0,
            1,
            [{
              offset: 0,
              color: "rgba(243,162,45, 0.6)"
            }, {
              offset: 0.6,
              color: "rgba(243,162,45, 0.2)"
            },
              {
                offset: 0.8,
                color: "rgba(243,162,45, 0.1)"
              }
            ],
            false
        ),
        shadowColor: "rgba(243,162,45, 0.1)",
        shadowBlur: 6
      }
    },
    data: dataList
  }]
};

// option && myChart.setOption(option);
// if (option && typeof option === "object") {
//   myChart.setOption(option, true);
//   //  refreshChart(myChart,option);
//   var index5 = 0; //播放所在下标
//   var mTime = setInterval(function () {
//     myChart.dispatchAction({
//       type: 'showTip',
//       seriesIndex: 0,
//       dataIndex: index5
//     });
//     index5++;
//     if (index5 >= 7) {
//       //console.log('data4', fxdata.length)
//       index5 = 0;
//       //console.log(fxdata)
//     }
//   }, 2500);
// }

onMounted(() => {
  myChart = echarts.init(myCharts)
  myChart.setOption(option)
})
</script>

<style scoped lang='less'>

</style>
