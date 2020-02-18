
<style lang="scss" scoped>
.PhoneNav {
  position: fixed;
  background-color: #fff;
  top: 0;
  left: 0;
  right: 0;
  z-index: 99;
}
.header {
  height: 70px;
  border-bottom: 1px solid #dcdfe6;
  padding: 0 20px;
}
.title {
  color: #00489a;
  font-size: 22px;
  margin-left: 4px;
  letter-spacing: 1px;
  font-weight: 320;
}
.logo-img {
  height: 28px;
}
.menu {
  cursor: pointer;
}
.menu-img {
  height: 30px;
}

// 小于865px隐藏
@media screen and(max-width:865px) {
  .phoneHide {
    display: block;
  }
}

// 大于865px显示
@media screen and(min-width:865px) {
  .phoneHide {
    display: none;
  }
}
// 菜单弹窗
.main {
  position: absolute;
  top: 70px;
  z-index: 99;
  width: 100vw;
  height: 280px;
  background: #fff;
  color: #000;
  border-bottom-left-radius: 4px;
  border-bottom-right-radius: 4px;
  overflow: hidden;
}
.main-item {
  font-size: 14px;
  height: 40px;
  line-height: 40px;
  padding: 0 20px;
  border-bottom: 1px solid #fff;
}
.item-active,
.main-item:hover {
  color: #00489a;
  background: #f0f0f0;
}
</style>
<template>
  <div class="PhoneNav phoneHide">
    <header class="header flex justify-between align-center">
      <nuxt-link class="logo" to="/">
        <img class="logo-img" src="~/assets/logo.png" alt="logo" />
      </nuxt-link>
      <h1 class="title">尊福机械</h1>
      <div class="menu" @click="mainSwitch = !mainSwitch">
        <img class="menu-img" src="~/assets/menu.svg" alt />
      </div>
    </header>

    <el-collapse-transition>
      <main class="main" v-show="mainSwitch">
        <nuxt-link v-for="(item,index) in navList" :key="index" :to="item.link">
          <div
            :class="activeIndex===index?'item-active':''"
            class="main-item"
            @click="clickItem(index)"
          >{{item.name}}</div>
        </nuxt-link>
      </main>
    </el-collapse-transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mainSwitch: false,
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
  methods: {
    clickItem(index) {
      this.activeIndex = index
      this.mainSwitch = false
    }
  }
}
</script>
