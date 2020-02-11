<template>
  <div class="flex-text-between header">
    <!-- 左侧logo -->
    <div class="logo flex align-center">
      <img class="logo-img" src="~/assets/logo.png" alt="logo" />
      <h1 class="logo-h1">尊福机械</h1>
    </div>
    <!-- 右侧导航 -->
    <nav class="items flex">
      <nuxt-link v-for="(item,index) in navList" :key="index" :to="item.link">
        <div
          :class="activeIndex===index?'item-active':''"
          class="item"
          @click="activeIndex=index"
        >{{item.name}}</div>
      </nuxt-link>
    </nav>
  </div>
</template>
<script>
export default {
  data() {
    return {
      activeIndex: 0,
      navList: [
        { name: '首页', link: '/' },
        { name: '公司简介', link: '/company' },
        { name: '产品展示', link: '/product' },
        { name: '设备展示', link: '/facility' },
        { name: '工厂展示', link: '/factory' },
        { name: '在线留言', link: '/note' },
        { name: '联系我们', link: '/contactUs' }
      ]
    }
  },
  methods: {}
}
</script>
<style lang="scss" scoped>
.header {
  font-size: 16px;
  height: 70px;
  border-bottom: 1px solid #dcdfe6;
  margin-bottom: 10px;
}
.logo {
}
.logo-img {
  height: 40px;
}
.logo-h1 {
  color: #00489a;
  font-size: 20px;
  margin-left: 4px;
  letter-spacing: 1px;
}

.item {
  width: 100px;
  text-align: center;
  cursor: pointer;
  height: 70px;
  line-height: 70px;
}
.item-active {
  font-weight: 600;
  color: #00489a;
}
.item:hover {
  font-weight: 600;
  color: #00489a;
}
</style>
