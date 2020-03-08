<template>
<view class="search" :class="{focused: isFocused}">
      <view class="input-box">
        <input type="text" @focus="goSearch" />
      </view>
      <view class="content"></view>
</template>
<script>
export default {
    data(){
        return{
            isFocused:false
        }
    },
    methods:{
        goSearch(){
            console.log("hello")
            // 当输入获取焦点是,在父元素添加一个类名
            this.isFocused=true
        }
    }
}
</script>
<style lang="less">
    .search{
        .input-box{
            background-color: #FF2D4A;
            padding:20rpx 16rpx;
            input{
                background-color: #fff;
            }
        }
        &focused{
            .input-box{
        background-color: #eee;
    }
        }
    }
</style>