<template>
  <view class="container" :style="{height:pageHeight,overflow:'hidden'}">
    <search  @window-height='handleWindowHeight'/>
    <swiper indicator-dots>
      <swiper-item :key="item.goods_id" v-for="item in swiperData">
        <image :src="item.image_src"/>
      </swiper-item>
    </swiper>
    <view class="navs">
      <navigator url="" :key="index" v-for="(item,index) in navsData">
        <image :src="item.image_src  "></image>
       </navigator>
     
    </view>
    <view class="floors">
      <view class="floor" :key="index" v-for="(item,index)in floorData">
        <view class="title">
          <image :src="floor_title.image_src">
        </view>
        <view class="items">
          <navigator url="" :key="i" v-for="(img,i) in item.product_list">
            <image src="img.image_src"/>
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
      cons0ole.log('handleWindowHeight')
    },
    querySwiperData(){
      wx.request({
        url:'http://api-ugo-dev.iteima.net/api/public/v1/home/swiperdata',
        success:(res)=>{
          this.swiperData=res.data.message
        }
      })
    },
    queryNavsData(){
      wx.request({
        url:'http://api-ugo-dev.iteima.net/api/public/v1/home/catitems',
        success:(res)=>{
          this.navsData=res.data.message
        }
      })
    },
    queryFloorData(){
      wx.request({
        url:'http://api-ugo-dev.iteima.net/api/public/v1/home/FloorData',
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
