<template>
  <el-card shadow="never" :body-style="{ paddingRight: '0px', paddingBottom:'0px' }">
    <div slot="header">
      <div class="flex-text-between">
        <span>产品展示</span>
        <el-button type="text">查看更多</el-button>
      </div>
    </div>

    <div class="products">
      <div class="product" v-for="(item,index) in productList" :key="index">
        <el-card shadow="hover" :body-style="{ padding: '0px' }">
          <div class="product-img">
            <img :src="item.url" :alt="item.name" />
          </div>
          <div class="product-bottom text-ellipsis">{{item.name}}</div>
        </el-card>
      </div>
    </div>
  </el-card>
</template>

<script>
let url = 'http://www.zf-vip.com/uploadpic/2016923643453206101.jpg'
export default {
  data() {
    return {
      productList: [
        {
          name: '产品1',
          url: url
        },
        { name: '产品2', url: url },
        { name: '产品3', url: url },
        { name: '产品4', url: url },
        { name: '产品1', url: url },
        { name: '产品2', url: url },
        { name: '产品3', url: url },
        { name: '产品4', url: url }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.product {
  width: 16.6666666%;
  display: inline-block;
  padding-right: 20px;
  padding-bottom: 20px;
  cursor: pointer;
}
.product-img {
  width: 100%;
  height: 260px;
}
.product-img img {
  width: 100%;
  height: 100%;
}
.product-bottom {
  padding-left: 14px;
  font-size: 14px;
  height: 50px;
  line-height: 50px;
}
</style>