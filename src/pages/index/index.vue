<template>
  <view class="container">
    <view class="search">
      <view class="input-box">
        <input type="text" />
      </view>
      <view class="content"></view>
    </view>
    <swiper>
      <swiper-item>
        <image src="static/uploads/banner1.png"></image>
      </swiper-item>
      <swiper-item>
        <image src="static/uploads/banner2.png"></image>
      </swiper-item>
      <swiper-item>
        <image src="static/uploads/banner3.png"></image>
      </swiper-item>
    </swiper>
  </view>
</template>
<script>
export default {
  data() {
    return {
      title: 'NIHAO'
    }
    },
      onload(){
    },
    methods: {

    }
  }
</script>
<style lang="less">
.search{
  .input-box{
    background-color: #FF2D4A;
    padding: 20rpx 16rpx;
    input{
      background-color: #fff;
    }
  }
}
swiper{
  height: 340rpx;
  image{
    width: 750rpx;
    height: 340rpx;
  }
}
</style>