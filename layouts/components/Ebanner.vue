<template>
  <div class="banner">
    <el-carousel indicator-position="intside" height="320px">
      <el-carousel-item v-for="item in banners" :key="item.name">
        <div style="width:100%;height:100%">
          <img style="width:100%;height:100%;object-fit: cover;" fit="cover" :src="item.url" />
        </div>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      banners: [
        {
          name: 'bannerl',
          url: 'http://www.zf-vip.com/images/1.jpg'
        },
        {
          name: 'banner2',
          url: 'http://www.zf-vip.com/images/1.jpg'
        },
        {
          name: 'banner3',
          url: 'http://www.zf-vip.com/images/1.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.banner {
  margin-top: 70px;
}
</style>