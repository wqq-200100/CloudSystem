<template>
  <div class="common-layout">
    <!--  第一个版本    -->
<!--        <el-container>
          <el-container>
            <el-aside width="500px">
              <el-row class="tac">
                <el-col :span="12">
                  <h5 class="mb-2">
                    <img src="./img-1.png" style="width: 30px;" alt="">
                    <span style="font-size: 20px;font-weight: bold">云资源管理系统</span>
                  </h5>
                  <el-menu
                      default-active="2"
                      class="el-menu-vertical-demo"
                  >
                    <el-menu-item index="1">
                      <el-icon>
                        <icon-menu/>
                      </el-icon>
                      <span>用户首页</span>
                    </el-menu-item>

                    <el-menu-item index="2">
                      <el-icon>
                        <icon-menu/>
                      </el-icon>
                      <span>管理员首页</span>
                    </el-menu-item>

                    <el-menu-item index="3">
                      <el-icon>
                        <icon-menu/>
                      </el-icon>
                      <span>资源工单</span>
                    </el-menu-item>

                    <el-sub-menu index="21">
                      <template #title>
                        <el-icon>
                          <location/>
                        </el-icon>
                        <span>运维工单流程</span>
                      </template>
                      <el-menu-item-group>
                        <el-menu-item index="2-1">数据交互</el-menu-item>
                        <el-menu-item index="2-2">端口管理</el-menu-item>
                        <el-menu-item index="2-3">访问权限</el-menu-item>
                        <el-menu-item index="2-4">进出机房</el-menu-item>
                        <el-menu-item index="2-5">系统升级变更</el-menu-item>
                        <el-menu-item index="2-6">托管设备上下架</el-menu-item>
                        <el-menu-item index="2-7">压力安全测试</el-menu-item>
                        <el-menu-item index="2-8">其他事项工单</el-menu-item>
                      </el-menu-item-group>
                    </el-sub-menu>

                    <el-sub-menu index="5">
                      <template #title>
                        <el-icon>
                          <location/>
                        </el-icon>
                        <span>资源详情</span>
                      </template>
                      <el-menu-item-group>
                        <el-menu-item index="1-3">资源异常监控</el-menu-item>
                        <el-menu-item index="1-4">应用全过程数据采集</el-menu-item>
                      </el-menu-item-group>
                    </el-sub-menu>

                    <el-sub-menu index="6">
                      <template #title>
                        <el-icon>
                          <location/>
                        </el-icon>
                        <span>服务反馈</span>
                      </template>
                      <el-menu-item-group>
                        <el-menu-item index="1-6">自动化巡检</el-menu-item>
                        <el-menu-item index="1-7">云服务商考评反馈</el-menu-item>
                        <el-menu-item index="1-8">投诉处理服务</el-menu-item>
                      </el-menu-item-group>
                    </el-sub-menu>

                    <el-menu-item index="7">
                      <el-icon>
                        <icon-menu/>
                      </el-icon>
                      <span>运维类文件电子化管理</span>
                    </el-menu-item>
                  </el-menu>
                </el-col>
              </el-row>
            </el-aside>
            <el-main style="background: #e5e3e3;margin:80px -240px;height: 90%;">
              <aaaaa/>
            </el-main>
          </el-container>
        </el-container>-->

    <!--  第二个版本    -->
<!--<el-container>
      <el-header style="margin-left: -20px">
        <h5 class="mb-2" style="display: flex;align-items: center">
          <img src="./img-2.png" alt="" style="width: 40px">
          <span style="font-size: 23px;margin-left: 10px;">云资源管理系统</span>
        </h5>
      </el-header>

      <el-container style="margin-top: 10px;">
        <el-aside width="200px">
          <el-aside width="200px">
            <el-col>
              <el-menu
                  active-text-color="#ffd04b"
                  background-color="#545c64"
                  class="el-menu-vertical-demo"
                  default-active="2"
                  text-color="#fff"
              >
                <el-sub-menu index="1">
                  <template #title>
                    <span>业务上云</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="1-1">资源工单</el-menu-item>
                  </el-menu-item-group>

                  <el-sub-menu index="1-4">
                    <template #title>运维工单</template>
                    <el-menu-item index="1-4-1">数据交互</el-menu-item>
                    <el-menu-item index="1-4-2">端口管理</el-menu-item>
                    <el-menu-item index="1-4-3">访问权限</el-menu-item>
                    <el-menu-item index="1-4-4">进出机房</el-menu-item>
                    <el-menu-item index="1-4-5">系统升级变更</el-menu-item>
                    <el-menu-item index="1-4-6">托管设备上下架</el-menu-item>
                    <el-menu-item index="1-4-7">压力安全测试</el-menu-item>
                    <el-menu-item index="1-4-8">其他</el-menu-item>
                  </el-sub-menu>
                </el-sub-menu>

                <el-menu-item index="2">
                  <span>异常监控</span>
                </el-menu-item>

                <el-menu-item index="3">
                  <span>应用数据采集</span>
                </el-menu-item>

                <el-menu-item index="4">
                  <span>自动化巡检</span>
                </el-menu-item>

                <el-sub-menu index="5">
                  <template #title>
                    <span>考评反馈</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="5-1">综合评分</el-menu-item>
                    <el-menu-item index="5-2">投诉处理</el-menu-item>
                  </el-menu-item-group>
                </el-sub-menu>

                <el-menu-item index="6">
                  <span>文件管理</span>
                </el-menu-item>

                <el-sub-menu index="9">
                  <template #title>
                    <span>南北东西流量采集</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="9-1">流量数据</el-menu-item>
                    <el-menu-item index="9-2">知识图谱</el-menu-item>
                    <el-menu-item index="9-3">流量属性</el-menu-item>
                    <el-menu-item index="9-4">流量监控指标</el-menu-item>
                    <el-menu-item index="9-5">采集监控</el-menu-item>
                  </el-menu-item-group>
                </el-sub-menu>

              </el-menu>

            </el-col>
          </el-aside>
        </el-aside>
        <el-main style="background: rgb(245 244 238);height: 100vh;">
          <jiankongcaiji_b/>
        </el-main>
      </el-container>
    </el-container>-->
    <el-container>
      <el-header style="margin-left: -20px">
        <h5 class="mb-2" style="display: flex;align-items: center">
<!--          <img src="./logo.png" alt="" style="width: 40px">-->
          <span style="font-size: 23px;margin-left: 10px;">云管系统平台</span>
        </h5>
      </el-header>

      <el-container style="margin-top: 10px;">
        <el-aside width="200px">
          <el-aside width="200px">
            <el-col>
              <el-menu
                  active-text-color="#ffd04b"
                  background-color="#000"
                  class="el-menu-vertical-demo"
                  default-active="2"
                  text-color="#fff"
              >
                <el-sub-menu index="1">
                  <template #title>
                    <span>业务上云</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="1-1">资源工单</el-menu-item>
                  </el-menu-item-group>

                  <el-sub-menu index="1-4">
                    <template #title>运维工单</template>
                    <el-menu-item index="1-4-1">数据交互</el-menu-item>
                    <el-menu-item index="1-4-2">端口管理</el-menu-item>
                    <el-menu-item index="1-4-3">访问权限</el-menu-item>
                    <el-menu-item index="1-4-4">进出机房</el-menu-item>
                    <el-menu-item index="1-4-5">系统升级变更</el-menu-item>
                    <el-menu-item index="1-4-6">托管设备上下架</el-menu-item>
                    <el-menu-item index="1-4-7">压力安全测试</el-menu-item>
                    <el-menu-item index="1-4-8">其他</el-menu-item>
                  </el-sub-menu>
                </el-sub-menu>

                <el-menu-item index="2">
                  <span>异常监控</span>
                </el-menu-item>

                <el-menu-item index="3">
                  <span>应用数据采集</span>
                </el-menu-item>

                <el-menu-item index="4">
                  <span>自动化巡检</span>
                </el-menu-item>

                <el-sub-menu index="5">
                  <template #title>
                    <span>考评反馈</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="5-1">综合评分</el-menu-item>
                    <el-menu-item index="5-2">投诉处理</el-menu-item>
                  </el-menu-item-group>
                </el-sub-menu>

                <el-menu-item index="6">
                  <span>文件管理</span>
                </el-menu-item>

                <el-sub-menu index="9">
                  <template #title>
                    <span>南北东西流量采集</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="9-1">流量数据</el-menu-item>
                    <el-menu-item index="9-2">知识图谱</el-menu-item>
                    <el-menu-item index="9-3">流量属性</el-menu-item>
                    <el-menu-item index="9-4">流量监控指标</el-menu-item>
                    <el-menu-item index="9-5">采集监控</el-menu-item>
                  </el-menu-item-group>
                </el-sub-menu>

              </el-menu>

            </el-col>
          </el-aside>
        </el-aside>
        <el-main style="background: rgb(213,212,205);height: 100vh;">
          <jiankongcaiji_b/>
        </el-main>
      </el-container>
    </el-container>

    <!--  第三个版本    -->
<!--    <el-container>
      <el-header style="margin-left: -20px">
        <h5 class="mb-2" style="display: flex;align-items: center">
          <img src="./img-3.png" alt="" style="width: 40px">
          <span style="font-size: 23px;margin-left: 10px;">云资源管理系统</span>
        </h5>
      </el-header>

      <el-container style="margin-top: 10px;">
        <el-aside width="200px">
          <el-aside width="200px">
            <el-col>
              <el-menu
                  active-text-color="#ffd04b"
                  background-color="#0d376e"
                  class="el-menu-vertical-demo"
                  default-active="2"
                  text-color="#fff"
              >
                <el-menu-item index="1">
                  <span>资源工单</span>
                </el-menu-item>

                <el-sub-menu index="99">
                  <template #title>
                    <span>运维工单</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="99-1">数据交互</el-menu-item>
                    <el-menu-item index="99-2">端口管理</el-menu-item>
                    <el-menu-item index="99-3">访问权限</el-menu-item>
                    <el-menu-item index="99-4">进出机房</el-menu-item>
                    <el-menu-item index="99-5">系统升级变更</el-menu-item>
                    <el-menu-item index="99-6">托管设备上下架</el-menu-item>
                    <el-menu-item index="99-7">压力安全测试</el-menu-item>
                    <el-menu-item index="99-8">其他</el-menu-item>
                  </el-menu-item-group>
                </el-sub-menu>

                <el-menu-item index="2">
                  <span>异常监控</span>
                </el-menu-item>

                <el-menu-item index="3">
                  <span>应用数据采集</span>
                </el-menu-item>

                <el-menu-item index="4">
                  <span>自动化巡检</span>
                </el-menu-item>

                <el-sub-menu index="5">
                  <template #title>
                    <span>考评反馈</span>
                  </template>
                  <el-menu-item-group>
                    <el-menu-item index="5-1">综合评分</el-menu-item>
                    <el-menu-item index="5-2">投诉处理</el-menu-item>
                  </el-menu-item-group>
                </el-sub-menu>

                <el-menu-item index="6">
                  <span>文件管理</span>
                </el-menu-item>
              </el-menu>

            </el-col>
          </el-aside>
        </el-aside>
        <el-main style="background: #fff;height: 100vh;">
          <jiankong_C/>
        </el-main>
      </el-container>
    </el-container>-->
  </div>
</template>

<script setup>


// 第二版
//资源工单
import ziyuan_b from "./components/a-2/ye-wu-01.vue";
//数据交互
import jiaohu_b from "./components/a-2/jiao-hu-02.vue";
//端口管理
import duankou_b from "./components/a-2/duan-kou-03.vue";
//访问权限
import quanxian_b from "./components/a-2/quan-xian-04.vue";
//进出机房
import jinchu_b from "./components/a-2/jin-chu-05.vue";
// 系统升级变更
import shengji_b from "./components/a-2/sheng-ji-06.vue";
// 系统上下架
import shangjia_b from "./components/a-2/shang-jia-07.vue";
//压力安全测试
import ceshi_b from "./components/a-2/ce-shi-08.vue";
//其他事项
import qita_b from "./components/a-2/qi-ta-09.vue";
//异常监控
import jiankong_b from "./components/a-2/jian-kong-10.vue";
//数据采集
import caiji_b from "./components/a-2/cai-ji-11.vue";
//自动巡检
import xunjian_b from "./components/a-2/xun-jian-12.vue";
//考评反馈
import kaoping_b from "./components/a-2/kao-pin-13.vue";
//投诉处理
import tousu_b from "./components/a-2/tou-su-14.vue";
//文件管理
import wenjian_b from "./components/a-2/wen-jian-15.vue";


import aaaaa from "./components/a-1/aaaaa.vue";


//资源工单
import ziyuan_c from "./components/a-3/01-zi-yuan.vue";
//数据交互
import jiaohu_c from "./components/a-3/02-jiao-hu.vue";
//端口管理
import duankou_c from "./components/a-3/03-duankou.vue";
//访问权限
import quanxi_c from "./components/a-3/04-fangwen.vue";
//进出
import jinchu_c from "./components/a-3/05-jinchu.vue";
//升级
import shengji_c from "./components/a-3/06-shengji.vue";
//上下架
import shangjia_c from "./components/a-3/07-shangjia.vue";
//安全测试
import ceshi_c from "./components/a-3/08-ceshi.vue";
//其他
import qita_c from "./components/a-3/09-qita.vue";
//监控异常
import jiankong_C from "./components/a-3/10-jiankong.vue";
//数据采集
import caiji_c from "./components/a-3/11-caiji.vue";
//巡检
import xunjian_c from "./components/a-3/12-xunjian.vue";
import pingfen_c from "./components/a-3/13-pingfen.vue";
import tousu_c from "./components/a-3/14-tousu.vue";
import wenjian_c from "./components/a-3/15-wenjian.vue";
import tupu from "./components/a-3/16-tupu.vue";
import zhibiao from "./components/a-3/17-zhibiao.vue";
import jiankongcaiji_b from "./components/a-3/18-caijijiankong.vue";







// 第一版
//数据交互
import duankou from "./components/a-1/duan-kou.vue";
//端口管理
import jiaohu from "./components/a-1/jiao-hu.vue";
//访问权限
import quanxian from "./components/a-1/quan-xian.vue";
// 进出机房
import jinchu from "./components/a-1/jin-chu.vue";
// 托管设备上下架
import tuoguan from "./components/a-1/tuo-guan.vue";
//压力安全测试
import yali from "./components/a-1/ya-li.vue";
//其他事项
import qita from "./components/a-1/qi-ta.vue";
//资源异常监控
import jiankong from "./components/a-1/jian-kong.vue";
//应用全过程数据采集
import caiji from "./components/a-1/cai-ji.vue";
//自动化巡检
import xunjian from "./components/a-1/xun-jian.vue";
//云服务商考评反馈
import fankui from "./components/a-1/fan-kui.vue";
//投诉处理
import tousu from "./components/a-1/tou-su.vue";
//运维文件管理
import yunwei from "./components/a-1/yun-wei.vue";
import JinChu from "./components/a-1/jin-chu.vue";
import CeShi08 from "./components/a-2/ce-shi-08.vue";
import QiTa09 from "./components/a-2/qi-ta-09.vue";
import JianKong10 from "./components/a-2/jian-kong-10.vue";
import TouSu14 from "./components/a-2/tou-su-14.vue";
import XunJian12 from "./components/a-2/xun-jian-12.vue";
import ShangJia07 from "./components/a-2/shang-jia-07.vue";
import DuanKou03 from "./components/a-2/duan-kou-03.vue";
import CaiJi11 from "./components/a-2/cai-ji-11.vue";

</script>

<style scoped lang="less">
.common-layout {
  //background: #eee6e6;
  //background: #f7f5f5;
  background: #fff;
  height: 100vh;
}
</style>
