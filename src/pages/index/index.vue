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
        <image src="/static/uploads/banner1.png">
      </swiper-item>
      <swiper-item>
        <image src="/static/uploads/banner2.png">
      </swiper-item>
      <swiper-item>
        <image src="/static/uploads/banner3.png">
      </swiper-item>
    </swiper>
    <view class="navs">
      <navigator url="true">
        <image src="/static/uploads/icon_index_nav_1@2x.png"></image>
      </navigator>
      <navigator url="true">
        <image src="/static/uploads/icon_index_nav_2@2x.png">
      </navigator>
      <navigator url="">
        <image src="/static/uploads/icon_index_nav_3@2x.png">
      </navigator>
      <navigator url="">
        <image src="/static/uploads/icon_index_nav_4@2x.png">
      </navigator>
    </view>
    <view class="floors">
      <view class="floor">
        <view class="title">
          <image src="/static/uploads/pic_floor01_title.png">
        </view>
        <view class="items">
          <navigator url="">
            <image src="/static/uploads/pic_floor01_1@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_2@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_3@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_4@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_5@2x.png">
          </navigator>
        </view>
      </view>
    </view>
     <view class="floors">
      <view class="floor">
        <view class="title">
          <image src="/static/uploads/pic_floor01_title.png">
        </view>
        <view class="items">
          <navigator url="">
            <image src="/static/uploads/pic_floor01_1@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_2@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_3@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_4@2x.png">
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor01_5@2x.png">
          </navigator>
        </view>
      </view>
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
  align-items: center;
  navigator {
    width: 128rpx;
    height: 140rpx;
  }
}
.floor {
  .title {
    background-color: #f4f4f4;
    width: 750rpx;
    height: 60rpx;
    padding: 20rpx 0 0 10rpx;
    box-sizing: border-box;
  }
  .items {
    padding: 20rpx 16rpx;
    overflow: hidden;
    navigator {
      float: left;
      padding-left: 10rpx;
      &:first-child {
        width: 232rpx;
        height: 386rpx;
        padding-left: 0;
      }
      &:nth-child(2),
      &:nth-child(5) {
        width: 273rpx;
        height: 188rpx;
      }
      &:nth-child(3),
      &:nth-child(4) {
        width: 193rpx;
        height: 188rpx;
      }
      &:nth-last-child(-n + 2) {
        padding-top: 10rpx;
      }
    }
  }
}
</style>
