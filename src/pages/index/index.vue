<template>
  <view class="container" :style="{height:pageHeight,overflow:'hidden'}">
    <search  @window-height='handleWindowHeight'/>
    <swiper indicator-dots>
      <swiper-item :key="item.goos_id" v-for="item in swiperData">
        <image :src="item.image_src"/>
      </swiper-item>
    </swiper>
    <view class="navs">
      <navigator url="">
        <image src="/static/uploads/icon_index_nav_1@2x.png"></image>
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
import search from '@/components/search'
export default {
  data() {
    return {
    pageHeight:'auto',
    title: "NIHAO",
    swiperData:[],
    navsData:[],
    floorData:[]
    };
  },
  components:{
    search
  },
  onload() {
    this.querySwiperData()
    this.queryNavsData()
    this.floorData()
  },
  methods: {
    handleWindowHeight(data){
      this.pageHeight=data.height +'px';
      console.log('handleWindowHeight')
    },
    querySwiperData(){
      wx.request({
        url:'http://api-ugo-dev.iteima.net/api/public/v1/home/swiperdata',
        success(res){
          this.swiperData=res.data.message
        }
      })
    },
    queryNavsData(){
      wx.request({
        url:'',
        success:(res)=>{
          this.navsData=res.data.message
        }
      })
    }
  }
};
</script>
<style lang="less">
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
  height: 180rpx;
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
&:first-child {
		.items {
			navigator {
				width: 232rpx;
        height: 188rpx;
        &:first-child {
        	width: 232rpx;
          height: 386rpx;
        }
			}
		}
	}
</style>
