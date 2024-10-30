<script setup>
import { View } from "@element-plus/icons-vue";
import {  onMounted, ref, inject, computed } from "vue";
//通过inject使用echarts
const echarts = inject("echarts");

const info = ref();
var infoUser_one = ref(null)
const props = defineProps({
    isQuanPing:{
        type: Boolean,
        default: ''
    }
})
onMounted(() => {
    box_one_echarts()
    window.addEventListener("resize", () => {
        infoUser_one.resize()
    });
});
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
</script>

<template>
    <view class="box1_top">
        <view class="box1_content_header">
            <span>基本信息</span>
            <img
                :style="{width:props.isQuanPing?'443px' : '500px',
                                     height:props.isQuanPing?'220px' : '290px',}"
                src="@/assets/images/title_boder.png"
                alt=""
            >
        </view>
        <div ref="info" style="width: 100%; height: 100%;position: absolute;top: 0"></div>
    </view>
</template>

<style scoped lang="scss">
.box1_top{
    position: relative;
    margin-top: 30px;
    span{
        position: absolute;
        top: -10px;
        left: 25px;
    }
}
</style>
