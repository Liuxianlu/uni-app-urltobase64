<template>
  <view class="content">
    <image class="logo" :src="urlImage"></image>
    <button type="default" @tap="tapButton">点击</button>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        urlImage: ''
      }
    },
    methods: {
      tapButton() {
        uni.chooseImage({
          count: 1,
          success: res => {
            const base64 = this.urlTobase64(res.tempFilePaths[0]);
            console.log(res.tempFilePaths[0]);
            console.log(base64);
          }
        });
      },
      
      // uni-app 图片URL转BASE64
      urlTobase64(url) {
        const imgData = uni.getFileSystemManager().readFileSync(url, 'base64');
        const base64 = 'data:image/jpeg;base64,' + imgData;
        return base64;
      }
    }
  }
</script>

<style>
  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .logo {
    height: 200rpx;
    width: 200rpx;
    margin-top: 200rpx;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 50rpx;
  }
</style>
