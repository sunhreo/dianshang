<template>
  <view class="container">
    <view class="search">
      <view class="input-box">
        <input type="text" />
      </view>
      <view class="content"></view>
    </view>
    <swiper indicator-dots>
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
    <view class="navs">
      <navigator url="">
        <image src="/static/"></image>
      </navigator>
      <navigator url="">
        <image src=""></image>
      </navigator>
      <navigator url="">
        <image src=""></image>
      </navigator>
      <navigator url="">
        <image src=""></image>
      </navigator>
    </view>
  </view>
</template>
<script>
export default {
  data() {
    return {
      title: "NIHAO"
    };
  },
  onload() {},
  methods: {}
};
</script>
<style lang="less">
.search {
  .input-box {
    background-color: #ff2d4a;
    padding: 20rpx 16rpx;
    input {
      background-color: #fff;
    }
  }
}
swiper {
  height: 340rpx;
  image {
    width: 750rpx;
    height: 340rpx;
  }
}
.navs {
  display: flex;
  justify-content: space-between;
  padding: 0 30rpx;
  background-color: pink;
  align-items: center;
  navigator {
    width: 128rpx;
    height: 140rpx;
  }
}
</style>
