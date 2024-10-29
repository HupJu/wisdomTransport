<template>
    <view class="dashboard-container" id="screen">
        <view class="quanping" @click="getQuan">
            <img src="@/assets/images/quanping.png" alt="">
        </view>
        <view class="titlebar">
            交通执法监督指挥和行业管理信息系统
        </view>
        <view class="bottom">
            <view class="box box1">
                <view class="box1_top">
                    <view class="box1_content_header">
                        <span>基本信息</span>
                        <img
                            :style="{width:isQuanPing?'443px' : '500px',
                                     height:isQuanPing?'220px' : '290px',}"
                            src="@/assets/images/title_boder.png"
                            alt=""
                        >
                    </view>
                    <div ref="info" style="width: 100%; height: 100%;position: absolute;top: 0"></div>
                </view>
                <view class="box1_center">
                    <view class="box1_content_header">
                        <span>今日车辆数据</span>
                        <img :style="{width:isQuanPing?'443px' : '500px',
                                     height:isQuanPing?'220px' : '290px',}" src="@/assets/images/title_boder.png" alt="">
                    </view>
                    <div ref="info1" style="width: 100%; height: 100%;position: absolute;top: 20px"></div>
                </view>
                <view class="box1_bottom">
                    <view class="box1_content_header">
                        <span>超限超载车辆</span>
                        <img :style="{width:isQuanPing?'443px' : '500px',
                                     height:isQuanPing?'240px' : '290px',}" src="@/assets/images/title_boder.png" alt="">
                    </view>
                    <div ref="info2" style="width: 100%; height: 100%;position: absolute;top: 15px"></div>
                </view>
            </view>
            <view class="box box2">
                <view class="box2_bottom_map">
                    <img src="@/assets/images/mapbg.png" alt="">
                    <div class="box_map" ref="info_map" style="width: 644px;height: 540px"></div>
                </view>
                <view class="box2_bottom">
                    <view class="box1_content_header">
                        <span>实时数据</span>
                        <img :style="{width:isQuanPing?'644px' : '644px',
                                     height:isQuanPing?'260px' : '430px',}" src="@/assets/images/map_bottom.png" alt="">
                    </view>
                    <view class="table">
                        <table style="width: 100%">
                            <thead>
                                <tr style="width: 100%;display: flex">
                                    <th style="width: 16.6%;text-align: center">时间</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                            </thead>
                            <tbody id="t_body" class="t_body" :style="{width:'100%',height:isQuanPing?'208px' : '380px',display:'flex',flexDirection:'column',overflow:'scroll',justifyContent:'space-between'}">
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">2</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">3</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">4</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">5</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">6</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">7</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">8</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">9</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">10</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">11</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">12</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">13</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">14</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">15</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">16</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">17</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">18</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">19</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                                <tr style="width: 100%;display: flex;justify-content: space-between">
                                    <th style="width: 16.6%;text-align: center">20</th>
                                    <th style="width: 16.6%;text-align: center">车牌号</th>
                                    <th style="width: 16.6%;text-align: center">总重(kg)</th>
                                    <th style="width: 16.6%;text-align: center">限载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">超载(kg)</th>
                                    <th style="width: 16.6%;text-align: center">站点名称</th>
                                </tr>
                            </tbody>
                        </table>
                    </view>
                </view>
            </view>
            <view class="box box3">
                <view class="box1_top">
                    <view class="box1_content_header">
                        <span>基本信息</span>
                        <img :style="{width:isQuanPing?'443px' : '500px',
                                     height:isQuanPing?'220px' : '290px',}" src="@/assets/images/title_boder.png" alt="">
                    </view>
                    <view class="user_box">
                        <view :class="className" style="margin-top:5px" @click="touser()">
                            <img src="@/assets/images/is-user.png" alt="">
                            <view class="cardrt">
                                <view class="cardhead">用户总量</view>
                                <view class="cardtent">10</view>
                            </view>
                        </view>
                        <view :class="className" @click="touser()" style="margin-top: 5px;background-color: #ba22ec">
                            <img src="@/assets/images/is-device.png" alt="">
                            <view class="cardrt">
                                <view class="cardhead">站点数量</view>
                                <view class="cardtent">10</view>
                            </view>
                        </view>
                        <view :class="className" @click="touser()" style="background-color: #1ca3ff">
                            <img src="@/assets/images/is_truck.png" alt="">
                            <view class="cardrt">
                                <view class="cardhead">今日车辆</view>
                                <view class="cardtent">10</view>
                            </view>
                        </view>
                        <view :class="className" @click="touser()" style="background-color: #f39c11">
                            <img src="@/assets/images/is_overload.png" alt="">
                            <view class="cardrt">
                                <view class="cardhead">超载车辆</view>
                                <view class="cardtent">10</view>
                            </view>
                        </view>
                    </view>
                </view>
                <view class="box1_center">
                    <view class="box1_content_header">
                        <span>今日车辆数据</span>
                        <img :style="{width:isQuanPing?'443px' : '500px',
                        height:isQuanPing?'220px' : '290px',}" src="@/assets/images/title_boder.png" alt="">
                    </view>
                    <div ref="info3" style="width: 100%; height: 100%;position: absolute;top: 20px"></div>
                </view>
                <view class="box1_bottom">
                    <view class="box1_content_header">
                        <span>超限超载车辆</span>
                        <img :style="{width:isQuanPing?'443px' : '500px',
                                     height:isQuanPing?'240px' : '290px',}" src="@/assets/images/title_boder.png" alt="">
                    </view>
                    <div ref="info4" style="width: 100%; height: 100%;position: absolute;right:-10px"></div>
                </view>
            </view>
        </view>
    </view>
</template>

<script setup>
import {  onMounted, ref, inject, computed } from "vue";
import { View } from "@element-plus/icons-vue";
import screenfull from "screenfull";
import "echarts/map/js/china.js"
//通过inject使用echarts
const echarts = inject("echarts");

//通过ref获取html元素
const info = ref();
const info1 = ref();
const info2 = ref();
const info3 = ref();
const info4 = ref()
const info_map = ref()
const isQuanPing = ref(true);
var infoUser_one = ref(null)
var infoUser_two = ref(null)
var infoUser_there = ref(null)
var infoUser_sever = ref(null)
var infoUser_size = ref(null)
var infoMap = ref(null)

onMounted(() => {
    box_one_echarts()
    box_two_echarts()
    box_there_echarts()
    box3_two_echarts()
    box3_there_echarts()
    box2_map()
    window.onresize= ()=>{
        infoUser_one.resize()
        infoUser_two.resize()
        infoUser_there.resize()
        infoUser_sever.resize()
        infoUser_size.resize()
        infoMap.resize()
    }
});
const className = computed(() => {
    return isQuanPing.value ? 'one customcard' : 'two customcard'; // 根据 isQuan 的值返回对应的类名
});

const getQuan = ()=>{
    isQuanPing.value = !isQuanPing.value;
    let element = document.getElementById("screen"); //指定全屏区域元素
    screenfull.toggle(element); //全屏显示
};
const box_one_echarts = () => {
    // 渲染echarts的父元素
    var infoEl = info.value;
    //  light dark
    var userEc = echarts.init(infoEl, "light");
    infoUser_one = userEc
    // 指定图表的配置项和数据
    var option = {
        tooltip: {
            trigger: 'axis',
            axisPointer: {
                type: 'cross',
                label: {
                    backgroundColor: '#6a7985'
                }
            }
        },
        legend: {
            textStyle:{
                fontSize: 14,//字体大小
                color: '#ffffff'//字体颜色
            },
            top:25,
            data: ['车辆总数', '超载数量', '超限数量']
        },
        grid: {
            left: '3%',
            right: '4%',
            bottom: '3%',
            containLabel: true
        },
        xAxis: [
            {
                type: 'category',
                boundaryGap: false,
                axisLabel: {
                    show: true,
                    textStyle: {
                        color: '#ffffff'
                    }
                },
                data: ['星期一', '星期二', '星期三', '星期四', '星期五', '星期六', '星期天']
            }
        ],
        yAxis: [
            {
                axisLabel: {
                    show: true,
                    textStyle: {
                        color: '#ffffff'
                    }
                },
                type: 'value'
            }
        ],
        series: [
            {
                name: '车辆总数',
                type: 'line',
                stack: 'Total',
                areaStyle: {},
                emphasis: {
                    focus: 'series'
                },
                data: [120, 132, 101, 134, 90, 230, 210]
            },
            {
                name: '超载数量',
                type: 'line',
                stack: 'Total',
                areaStyle: {},
                emphasis: {
                    focus: 'series'
                },
                data: [220, 182, 191, 234, 290, 330, 310]
            },
            {
                name: '超限数量',
                type: 'line',
                stack: 'Total',
                areaStyle: {},
                emphasis: {
                    focus: 'series'
                },
                data: [150, 232, 201, 154, 190, 330, 410]
            }
        ]
    };
    // 使用刚指定的配置项和数据显示图表。
    userEc.setOption(option);
};
const box2_map = ()=>{
    var chinaGeoCoordMap = {
        黑龙江: [127.9688, 45.368],
        内蒙古: [110.3467, 41.4899],
        吉林: [125.8154, 44.2584],
        北京市: [116.4551, 40.2539],
        辽宁: [123.1238, 42.1216],
        河北: [114.4995, 38.1006],
        天津: [117.4219, 39.4189],
        山西: [112.3352, 37.9413],
        陕西: [109.1162, 34.2004],
        甘肃: [103.5901, 36.3043],
        宁夏: [106.3586, 38.1775],
        青海: [101.4038, 36.8207],
        新疆: [87.9236, 43.5883],
        西藏: [91.11, 29.97],
        四川: [103.9526, 30.7617],
        重庆: [108.384366, 30.439702],
        山东: [117.1582, 36.8701],
        河南: [113.4668, 34.6234],
        江苏: [118.8062, 31.9208],
        安徽: [117.29, 32.0581],
        湖北: [114.3896, 30.6628],
        浙江: [119.5313, 29.8773],
        福建: [119.4543, 25.9222],
        江西: [116.0046, 28.6633],
        湖南: [113.0823, 28.2568],
        贵州: [106.6992, 26.7682],
        云南: [102.9199, 25.4663],
        广东: [113.12244, 23.009505],
        广西: [108.479, 23.1152],
        海南: [110.3893, 19.8516],
        上海: [121.4648, 31.2891],
        喀什地区:[76.0117, 39.4896]
    };


    var chinaDatas = [
        // [
        //     {
        //         name: '黑龙江',
        //         value: 5,
        //     },
        // ],
        [
            {
                name: '内蒙古',
                value: 3,
            },
        ],
        // [
        //     {
        //         name: '北京市',
        //         value: 20,
        //     },
        // ],
        // [
        //     {
        //         name: '吉林',
        //         value: 3,
        //     },
        // ],
        // [
        //     {
        //         name: '辽宁',
        //         value: 5,
        //     },
        // ],
        // [
        //     {
        //         name: '河北',
        //         value: 6,
        //     },
        // ],
        // [
        //     {
        //         name: '天津',
        //         value: 5,
        //     },
        // ],
        [
            {
                name: '山西',
                value: 7,
            },
        ],
        [
            {
                name: '陕西',
                value: 6,
            },
        ],
        [
            {
                name: '甘肃',
                value: 5,
            },
        ],
        // [
        //     {
        //         name: '宁夏',
        //         value: 5,
        //     },
        // ],
        // [
        //     {
        //         name: '青海',
        //         value: 7,
        //     },
        // ],
        [
            {
                name: '新疆',
                value: 3,
            },
        ],
        // [
        //     {
        //         name: '西藏',
        //         value: 3,
        //     },
        // ],
        // [
        //     {
        //         name: '四川',
        //         value: 10,
        //     },
        // ],
        // [
        //     {
        //         name: '重庆',
        //         value: 9,
        //     },
        // ],
        [
            {
                name: '广东',
                value: 10,
            },
        ],
        [
            {
                name: '山东',
                value: 6,
            },
        ],
        [
            {
                name: '河南',
                value: 8,
            },
        ],
        [
            {
                name: '江苏',
                value: 10,
            },
        ],
        [
            {
                name: '安徽',
                value: 9,
            },
        ],
        [
            {
                name: '湖北',
                value: 10,
            },
        ],
        [
            {
                name: '浙江',
                value: 16,
            },
        ],
        // [
        //     {
        //         name: '福建',
        //         value: 9,
        //     },
        // ],
        //
        // [
        //     {
        //         name: '湖南',
        //         value: 14,
        //     },
        // ],
        [
            {
                name: '贵州',
                value: 8,
            },
        ],
        [
            {
                name: '广西',
                value: 7,
            },
        ],
        [
            {
                name: '喀什地区',
                value: 1,
            },
        ],
        // [
        //     {
        //         name: '海南',
        //         value: 7,
        //     },
        // ],
        // [
        //     {
        //         name: '上海',
        //         value: 17,
        //     },
        // ],
    ];


    var convertData = function (data) {
        var res = [];
        for (var i = 0; i < data.length; i++) {
            var dataItem = data[i];
            var fromCoord = chinaGeoCoordMap[dataItem[0].name];
            var toCoord = [113.4668, 34.6234];
            if (fromCoord && toCoord) {
                res.push([
                    {
                        coord: toCoord,
                        value: dataItem[0].value,
                    },
                    {
                        coord: fromCoord,
                    },
                ]);
            }
        }
        return res;
    };


    var series = [];
    [['新疆', chinaDatas]].forEach(function (item, i) {
        series.push(
            {
                type: 'lines',
                zlevel: 1,
                effect: {
                    show: true,
                    period: 10, //箭头指向速度，值越小速度越快
                    trailLength: 0.1, //特效尾迹长度[0,1]值越大，尾迹越长重
                    symbol: 'arrow', //箭头图标
                    symbolSize: 10, //图标大小
                },
                lineStyle: {
                    normal: {
                        width: 1, //尾迹线条宽度
                        opacity: 1, //尾迹线条透明度
                        curveness: 0.3, //尾迹线条曲直度
                    },
                },
                data: convertData(item[1]),
            },
            {
                type: 'effectScatter',
                coordinateSystem: 'geo',
                zlevel: 2,
                rippleEffect: {
                    //涟漪特效
                    period: 15, //动画时间，值越小速度越快
                    brushType: 'stroke', //波纹绘制方式 stroke, fill
                    scale: 5, //波纹圆环最大限制，值越大波纹越大
                },
                label: {
                    normal: {
                        show: true,
                        position: 'right', //显示位置
                        offset: [5, 0], //偏移设置
                        formatter: function (params) {
                            //圆环显示文字
                            return params.data.name;
                        },
                        fontSize: 10,
                    },
                    emphasis: {
                        show: true,
                    },
                },
                symbol: 'circle',
                symbolSize: function (val) {
                    return 3 + val[2] * 1; //圆环大小
                },
                itemStyle: {
                    normal: {
                        show: false,
                        color: '#FFA54F',
                    },
                },
                data: item[1].map(function (dataItem) {
                    return {
                        name: dataItem[0].name,
                        value: chinaGeoCoordMap[dataItem[0].name].concat([dataItem[0].value]),
                    };
                }),
            },
            //被攻击点
            {
                type: 'scatter',
                coordinateSystem: 'geo',
                zlevel: 2,
                rippleEffect: {
                    period: 4,
                    brushType: 'stroke',
                    scale: 4,
                },
                label: {
                    normal: {
                        show: true,
                        position: 'right',
                        //offset:[5, 0],
                        color: '#0f0',
                        formatter: '{b}',
                        textStyle: {
                            color: '#0f0',
                        },
                    },
                    emphasis: {
                        show: true,
                        color: '#FFA54F',
                    },
                },
                symbol: 'pin',
                symbolSize: 50,
                data: [
                    {
                        name: item[0],
                        value: chinaGeoCoordMap[item[0]].concat([10]),
                    },
                ],
            }
        );
    });
    var infoEl = info_map.value;
    //  light dark
    var userEc = echarts.init(infoEl, "light");
    infoMap = userEc
    var option = {
        tooltip: {
            trigger: 'item',
            backgroundColor: 'rgba(166, 200, 76, 0.82)',
            borderColor: '#FFFFCC',
            showDelay: 0,
            hideDelay: 0,
            enterable: true,
            transitionDuration: 0,
            extraCssText: 'z-index:100',
            formatter: function (params, ticket, callback) {
                //根据业务自己拓展要显示的内容
                var res = '';
                var name = params.name;
                var value = params.value[params.seriesIndex + 1];
                if(value == undefined){
                    return
                }else{
                    res = "<span style='color:#fff;'>" + name + '</span><br/>数据：' + value;
                    return res;
                }
            },
        },
        visualMap: {
            //图例值控制
            min: 1,
            max: 30,
            bottom:'3%',
            left:20,
            calculable: true,
            show: true,
            color: ['#f44336', '#fc9700', '#ffde00', '#ffde00', '#00eaff'],
            textStyle: {
                color: '#fff',
            },
        },
        geo: {
            map: 'china',
            zoom: 1.2,
            label: {
                emphasis: {
                    show: false,
                },
            },
            roam: true, //是否允许缩放
            itemStyle: {
                normal: {
                    color: '#141833', //地图背景色
                    borderColor: '#00fcff', //省市边界线00fcff 516a89
                    borderWidth: 1,
                },
                emphasis: {
                    color: '#13297B', //悬浮背景
                },
            },
        },
        series: series,
    };
    userEc.setOption(option);
    window.addEventListener("userEc", function (event) {
        userEc.resize();
    })
};
const box_two_echarts = () => {
    // 渲染echarts的父元素
    var infoEl = info1.value;
    //  light dark
    var userEc = echarts.init(infoEl, "light");
    infoUser_two = userEc
    // 指定图表的配置项和数据
    var option = {
        title: {
            text: '今日车辆数据',
            left: 'center',
            textStyle:{
                color: '#fff'
            }
        },
        tooltip: {
            trigger: 'item'
        },
        legend: {
            textStyle:{
                fontSize: 14,//字体大小
                color: '#ffffff'//字体颜色
            },
            orient: 'vertical',
            left: 'left'
        },
        series: [
            {
                name: '数据信息',
                type: 'pie',
                radius: '50%',
                data: [
                    { value: 1048, name: '超载数量' },
                    { value: 735, name: '未超载数量' }
                ],
                emphasis: {
                    itemStyle: {
                        shadowBlur: 10,
                        shadowOffsetX: 0,
                        shadowColor: 'rgba(0, 0, 0, 0.5)'
                    }
                }
            }
        ]
    };
    // 使用刚指定的配置项和数据显示图表。
    userEc.setOption(option);
};
const box_there_echarts = () => {
    // 渲染echarts的父元素
    var infoEl = info2.value;
    //  light dark
    var userEc = echarts.init(infoEl, "light");
    infoUser_there = userEc
    // 指定图表的配置项和数据
    var option = {
        tooltip: {},
        grid: {
            top: '8%',
            left: '1%',
            right: '1%',
            bottom: '8%',
            containLabel: true,
        },
        legend: {
            itemGap: 50,
            top:-5,
            data: ['超载总量' ,'最新超载量'],
            textStyle: {
                color: '#f9f9f9',
                borderColor: '#fff'
            },
        },
        xAxis: [{
            type: 'category',
            boundaryGap: true,
            axisLine: { //坐标轴轴线相关设置。数学上的x轴
                show: true,
                lineStyle: {
                    color: '#f9f9f9'
                },
            },
            axisLabel: { //坐标轴刻度标签的相关设置
                textStyle: {
                    color: '#d1e6eb',
                    margin: 15,
                },
            },
            axisTick: {
                show: false,
            },
            data: ['1月', '2月', '3月', '4月', '5月', '6月', '7月', ],
        }],
        yAxis: [{
            type: 'value',
            min: 0,
            // max: 140,
            splitNumber: 7,
            splitLine: {
                show: true,
                lineStyle: {
                    color: '#0a3256'
                }
            },
            axisLine: {
                show: false,
            },
            axisLabel: {
                margin: 20,
                textStyle: {
                    color: '#d1e6eb',

                },
            },
            axisTick: {
                show: false,
            },
        }],
        series: [{
            name: '超载总量',
            type: 'line',
            // smooth: true, //是否平滑曲线显示
            // 			symbol:'circle',  // 默认是空心圆（中间是白色的），改成实心圆
            showAllSymbol: true,
            symbol: 'emptyCircle',
            symbolSize: 6,
            lineStyle: {
                normal: {
                    color: "#28ffb3", // 线条颜色
                },
                borderColor: '#f0f'
            },
            label: {
                show: true,
                position: 'top',
                textStyle: {
                    color: '#fff',
                }
            },
            itemStyle: {
                normal: {
                    color: "#28ffb3",

                }
            },
            tooltip: {
                show: false
            },
            areaStyle: { //区域填充样式
                normal: {
                    //线性渐变，前4个参数分别是x0,y0,x2,y2(范围0~1);相当于图形包围盒中的百分比。如果最后一个参数是‘true’，则该四个值是绝对像素位置。
                    color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                        offset: 0,
                        color: 'rgba(0,154,120,1)'
                    },
                        {
                            offset: 1,
                            color: 'rgba(0,0,0, 0)'
                        }
                    ], false),
                    shadowColor: 'rgba(53,142,215, 0.9)', //阴影颜色
                    shadowBlur: 20 //shadowBlur设图形阴影的模糊大小。配合shadowColor,shadowOffsetX/Y, 设置图形的阴影效果。
                }
            },
            data: [393, 438, 485, 631, 689, 824, 907]
        }, {
            name: '最新超载量',
            type: 'bar',
            barWidth: 20,
            tooltip: {
                show: false
            },
            label: {
                show: true,
                position: 'top',
                textStyle: {
                    color: '#fff',
                }
            },
            itemStyle: {
                normal: {
                    color: function(params) {
                        var colorList = ['#0ec1ff', '#10cdff', '#12daff', '#15ebff', '#17f8ff', '#1cfffb', '#1dfff1'];
                        return colorList[params.dataIndex];
                    }
                }
            },
            data: [200, 382, 102, 267, 186, 315, 316]
        }]
    };
    // 使用刚指定的配置项和数据显示图表。
    userEc.setOption(option);
};
const box3_two_echarts = ()=>{
    // 渲染echarts的父元素
    var infoEl = info3.value;
    //  light dark
    var userEc = echarts.init(infoEl, "light");
    infoUser_size = userEc
    // 指定图表的配置项和数据
    var option = {
        tooltip: {
            trigger: 'axis',
            axisPointer: {
                type: 'shadow'
            }
        },
        legend: {
            textStyle:{
                fontSize: 14,//字体大小
                color: '#ffffff'//字体颜色
            },
        },
        grid: {
            left: '3%',
            right: '4%',
            containLabel: true
        },
        xAxis: {
            type: 'value',
            boundaryGap: [0, 0.01],
            axisLabel:{
                textStyle: {
                    color: '#fff',
                }
            }
        },
        yAxis: {
            type: 'category',
            data: ['金乡','无锡','武汉'],
            axisLabel:{
                textStyle: {
                    color: '#fff',
                }
            }
        },
        series: [
            {
                name: '金乡',
                type: 'bar',
                data: [18203, 23489, 29034]
            },
            {
                name: '无锡',
                type: 'bar',
                data: [19325, 23438, 31000]
            },
            {
                name: '武汉',
                type: 'bar',
                data: [19325, 23438, 31000]
            },
        ]
    }
    userEc.setOption(option);
};
const box3_there_echarts = ()=> {
    // 渲染echarts的父元素
    var infoEl = info4.value;
    //  light dark
    var userEc = echarts.init(infoEl, "light");
    infoUser_sever = userEc
    var series = [
        {
            data: [120, 200, 150, 80, 70, 110, 130],
            type: 'bar',
            stack: 'a',
            name: 'a'
        },
        {
            data: [10, 46, 64, '-', 0, '-', 0],
            type: 'bar',
            stack: 'a',
            name: 'b'
        },
        {
            data: [30, '-', 0, 20, 10, '-', 0],
            type: 'bar',
            stack: 'a',
            name: 'c'
        },
        {
            data: [30, '-', 0, 20, 10, '-', 0],
            type: 'bar',
            stack: 'b',
            name: 'd'
        },
        {
            data: [10, 20, 150, 0, '-', 50, 10],
            type: 'bar',
            stack: 'b',
            name: 'e'
        }
    ];
    const stackInfo = {};
    for (let i = 0; i < series[0].data.length; ++i) {
        for (let j = 0; j < series.length; ++j) {
            const stackName = series[j].stack;
            if (!stackName) {
                continue;
            }
            if (!stackInfo[stackName]) {
                stackInfo[stackName] = {
                    stackStart: [],
                    stackEnd: []
                };
            }
            const info = stackInfo[stackName];
            const data = series[j].data[i];
            if (data && data !== '-') {
                if (info.stackStart[i] == null) {
                    info.stackStart[i] = j;
                }
                info.stackEnd[i] = j;
            }
        }
    }
    for (let i = 0; i < series.length; ++i) {
        const data = series[i].data;
        const info = stackInfo[series[i].stack];
        for (let j = 0; j < series[i].data.length; ++j) {
            // const isStart = info.stackStart[j] === i;
            const isEnd = info.stackEnd[j] === i;
            const topBorder = isEnd ? 20 : 0;
            const bottomBorder = 0;
            data[j] = {
                value: data[j],
                itemStyle: {
                    borderRadius: [topBorder, topBorder, bottomBorder, bottomBorder]
                }
            };
        }
    }
    // 指定图表的配置项和数据
    var option = {
        xAxis: {
            axisLabel: {
                show: true,
                textStyle: {
                    color: '#ffffff'
                }
            },
            type: 'category',
            data: ['星期一', '星期二', '星期三', '星期四', '星期五', '星期六', '星期天']
        },
        yAxis: {
            axisLabel: {
                show: true,
                textStyle: {
                    color: '#ffffff'
                }
            },
            type: 'value'
        },
        series: series
    }

    userEc.setOption(option);
}
</script>

<style scoped lang="scss">
    .dashboard-container {
        position: relative;
        display: flex;
        flex-direction: column;
        width: 100%;
        height: calc(100vh - 84px);
        background-color: #141833;
        .quanping{
            position: absolute;
            right: 10px;
            top: 10px;
            cursor: pointer;
            img{
                width: 20px;
                height: 20px;
            }
        }
        .titlebar {
            height: 6.4vh;
            line-height: 6.4vh;
            background: url(@/assets/images/titlebg.png) no-repeat bottom;
            background-size: 100%;
            color: #fff;
            font-size: 1.22vw;
            text-align: center;
            text-shadow: 0.21vh 0.1vw 0.64vh #58d5db;
        }
        .bottom{
            display: flex;
            justify-content: space-between;
            height: 100%;
            color: #fff;
            .box1{
                display: flex;
                flex-direction: column;
                padding-left: 3%;
                //img{
                //    width: 27vw;
                //    height: 27vh;
                //}
                .box1_top{
                    position: relative;
                    margin-top: 30px;
                    span{
                        position: absolute;
                        top: -10px;
                        left: 25px;
                    }
                }
                .box1_center{
                    position: relative;
                    margin-top: 30px;
                    span{
                        position: absolute;
                        top: -10px;
                        left: 25px;
                    }
                }
                .box1_bottom{
                    position: relative;
                    margin-top: 30px;
                    display: flex;
                    justify-content: center;
                    span{
                        position: absolute;
                        top: -10px;
                        left: 25px;
                    }
                }
            }
            .box2{
                display: flex;
                flex-direction: column;
                .box2_bottom_map{
                    position: relative;
                    img{
                    }
                    .box_map{
                        position: absolute;
                        top: 0;
                    }
                }
                .box2_bottom{
                    position: relative;
                    margin-top: 8px;
                    height: 260px;
                    //overflow: hidden;

                    span{
                        position: absolute;
                        top: 0;
                        left: 50%;
                        transform: translateX(-50%);
                    }
                    .table{
                        position: absolute;
                        top: 0;
                        width: 100%;
                        margin-top: 20px;
                        text-align: center;
                        padding: 0 10px;
                        .t_body::-webkit-scrollbar {
                            display: none; /* Chrome Safari */
                        }
                    }

                }
            }
            .box3{
                display: flex;
                flex-direction: column;
                padding-right: 3%;
                .box1_top{
                    position: relative;
                    margin-top: 30px;
                    span{
                        position: absolute;
                        top: -10px;
                        left: 25px;
                    }
                    .user_box{
                        position: absolute;
                        top: 8%;
                        display: flex;
                        flex-wrap: wrap;
                        justify-content: space-around;
                        color: #fff;
                        .one{
                            padding:2px 30px;
                        }
                        .two{
                            padding:15px 45px;
                        }
                        .customcard{
                            display: flex;
                            align-items: center;
                            background-color: #0bdef1;
                            border-radius: 6px;
                            margin-top: 15px;
                            .cardrt{
                                display: flex;
                                flex-direction: column;
                                padding-left: 10px;
                                .cardtent{
                                    font-size: 40px;
                                    font-weight: 700;
                                }
                            }
                        }
                    }
                }
                .box1_center{
                    position: relative;
                    margin-top: 30px;
                    span{
                        position: absolute;
                        top: -10px;
                        left: 25px;
                    }
                    //img{
                    //    width: 27vw;
                    //    height: 27vh;
                    //}
                }
                .box1_bottom{
                    position: relative;
                    margin-top: 30px;
                    display: flex;
                    justify-content: center;
                    span{
                        position: absolute;
                        top: -10px;
                        left: 25px;
                    }
                    //img{
                    //    width: 27vw;
                    //    height: 27vh;
                    //}
                }
            }
        }
    }
</style>
