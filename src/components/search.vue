<template>
  <view class="search" :class="{focused: isFocused}">
    <view class="input-box">
      <input :placeholder="placeholder" type="text" @focus="goSearch" />
      <text class="cancel" @click="handleCancel">取消</text>
    </view>
    <view class="content" :style="{height:pageHeight,overflow:'hidden'}"></view>
  </view>
</template>
<script>
export default {
  data() {
    return {
      isFocused: false,
      placeholder: ''
    }
  },
  onLoad() {
    const { windowHeight } = uni.getSystemInfoSync()
    console.log(windowHeight)
  },
  methods: {
    goSearch() {
      const { windowHeight } = uni.getSystemInfoSync()
      console.log("hello")
      this.$emit("window-Height", {
        height: uni.getSystemInfoSync().windowHeight
      });
      // 当输入获取焦点是,在父元素添加一个类名
      this.isFocused = true
      this.placeholder = '请输入想要的商品'
    },
    handleCancel() {
      // 取消
      this.$emit('search', {
        pageHeight: 'auto'
      })
      this.isFocused = false
      this.placeholder = ''
    }
  }
}
</script>
<style lang="less">
.search {
  .content {
    position: absolute;
    top: 94rpx;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 9;
    background-color: #fff;
    display: none;
  }
  .input-box {
    background-color: #ff2d4a;
    padding: 20rpx 16rpx;
    display: flex;
    height: 60rpx;
    position: relative;
    input {
      flex: 1;
      padding-left: 55rpx;
      height: 60rpx;
      background-color: #fff;
    }
    .cancel {
      display: none;
    }
    &::before {
      content: "";
      display: none;
      width: 32rpx;
      height: 32rpx;
      position: absolute;
      top: 50%;
      transform: translate(15rpx, -50%);
      background-image: url("http://static.botue.com/ugo/images/icon_search%402x.png");
      background-size: 32rpx;
    }
    &::after {
      content: "搜索";
      position: absolute;
      left: 50%;
      top: 50%;
      padding-left: 40rpx;
      transform: translate(-50%, -50%);
      font-size: 24rpx;
      color: #ccc;
      background-image: url("http://static.botue.com/ugo/images/icon_search%402x.png");
      background-size: 32rpx;
      background-repeat: no-repeat;
    }
  }
  &.focused {
    .content {
      display: block;
    }
    .input-box {
      background-color: #eee;
      &::after {
        display: none;
      }
      &::before {
        display: block;
      }
    }
    .cancel {
      display: block;
      width: 100rpx;
      height: 50rpx;
      line-height: 50rpx;
      text-align: center;
      font-size: 30rpx;
    }
  }
}
</style>