<template>
  <view class="search" :class='{focused: isFocused}'>
    <!-- 搜索栏标签 -->
    <view class="input-box">
      <input :placeholder='placeholder' type="text" @focus='goSearch'/>
      <text class='cancel' @click='handleCancel'>取消</text>
    </view>
    <!-- 搜索的结果 -->
    <view class="content">
      <!-- 标题 -->
      <div class="title">
        搜索历史
        <span class="clear"></span>
      </div>
      <!-- 搜索历史关键字 -->
      <div class="history">
        <navigator url=''>小米</navigator>
        <navigator url=''>华为</navigator>
        <navigator url=''>苹果</navigator>
      </div>
      <!-- 搜索结果 -->
      <!-- <scroll-view scroll-y class="result">
        <navigator url=''>冰箱</navigator>
      </scroll-view> -->
    </view>
  </view>
</template>
<script>
export default {
  data () {
    return {
      isFocused: false,
      placeholder: ''
    }
  },
  methods: {
    goSearch () {
      const { windowHeight } = uni.getSystemInfoSync()
      // 将可视区高度传递到父组件
      this.$emit('window-height', {height: windowHeight})
      // 当输入框获取焦点时，在父元素添加一个类名 focused
      this.isFocused = true
      this.placeholder = '请输入想要的商品'
    },
    handleCancel () {
      // 点击取消按钮恢复原始状态
      this.$emit('window-height', {height: 'auto'})
      // 取消动作：恢复原始状态
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
    padding: 30rpx;
    .title {
      font-size: 27rpx;
      line-height: 1;
      color: #333;
    }
    .clear {
      display: block;
      width: 27rpx;
      height: 27rpx;
      float: right;
      background-image: url(http://static.botue.com/ugo/images/clear.png);
      background-size: cover;
    }
    .history {
      padding-top: 30rpx;
      navigator {
        display: inline-block;
        line-height: 1;
        padding: 15rpx 20rpx 12rpx;
        background-color: #ddd;
        font-size: 24rpx;
        margin-right: 20rpx;
        margin-bottom: 15rpx;
        color: #333;
      }
    }
  }
  .input-box {
    background-color: #FF2D4A;
    padding: 20rpx 16rpx;
    display: flex;
    position: relative;
    input {
      background-color: #fff;
      padding-left: 55rpx;
      height: 60rpx;
      flex: 1;
    }
    .cancel {
      display: none;
    }

    &::before {
      content: '';
      display: none;
      width: 32rpx;
      height: 32rpx;
      position: absolute;
      top: 50%;
      transform: translate(15rpx, -50%);
      background-image: url('http://static.botue.com/ugo/images/icon_search%402x.png');
      background-size: 32rpx;
    }

    &::after {
      content: '搜索';
      position: absolute;
      left: 50%;
      top: 50%;
      padding-left: 40rpx;
      transform: translate(-50%, -50%);
      font-size: 24rpx;
      color: #ccc;
      background-image: url('http://static.botue.com/ugo/images/icon_search%402x.png');
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