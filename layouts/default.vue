<template>
  <div class="layout">
    <NavMenu name="头部导航" />
    <Ebanner name="轮播图" />
    <main class="main" name="主体部分">
      <nuxt />
    </main>
    <Efooter name="底部版权" />
  </div>
</template>
<script>
import NavMenu from './components/NavMenu'
import Efooter from './components/Efooter'
import Ebanner from './components/Ebanner'

export default {
  components: { NavMenu, Efooter, Ebanner },
  data() {
    return {}
  }
}
</script>
<style lang="scss" scoped>
.layout {
  width: 1300px;
  margin: 0 auto;
  overflow: hidden;
}
.main {
  min-height: 55vh;
}
</style>