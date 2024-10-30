<script setup>
import { View } from "@element-plus/icons-vue";
import {  onMounted, ref, inject, computed } from "vue";
//通过inject使用echarts
const echarts = inject("echarts");
const info1 = ref();
var infoUser_two = ref(null)
const props = defineProps({
    isQuanPing:{
        type: Boolean,
        default: ''
    }
})
onMounted(() => {
    console.log('111')
    box_two_echarts()
    window.addEventListener("resize", () => {
        infoUser_two.resize()
    });
});
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
</script>

<template>
    <view class="box1_center">
        <view class="box1_content_header">
            <span>今日车辆数据</span>
            <img :style="{width:props.isQuanPing?'443px' : '500px',
                                     height:props.isQuanPing?'220px' : '290px',}" src="@/assets/images/title_boder.png" alt="">
        </view>
        <div ref="info1" style="width: 100%; height: 100%;position: absolute;top: 20px"></div>
    </view>
</template>

<style scoped lang="scss">
.box1_center{
    position: relative;
    margin-top: 30px;
    span{
        position: absolute;
        top: -10px;
        left: 25px;
    }
}
</style>
