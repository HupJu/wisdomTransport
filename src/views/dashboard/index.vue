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
                <basic :isQuanPing="isQuanPing"></basic>
                <boxCenter :isQuanPing="isQuanPing"></boxCenter>
                <boxBottom :isQuanPing="isQuanPing"></boxBottom>
            </view>
            <view class="box box2">
                <boxMap></boxMap>
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
import basic from "../../components/Basic/index.vue"
import boxCenter from "../../components/Basic/boxCenter.vue"
import boxBottom from "../../components/Basic/boxBottom.vue"
import boxMap from "../../components/Basic/map.vue"

//通过ref获取html元素
const info3 = ref();
const info4 = ref()
const isQuanPing = ref(true);
var infoUser_sever = ref(null)
var infoUser_size = ref(null)

onMounted(() => {
    box3_two_echarts()
    box3_there_echarts()
    window.onresize= ()=>{
        infoUser_sever.resize()
        infoUser_size.resize()
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

            }
            .box2{
                display: flex;
                flex-direction: column;
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
