<template>
  <div class="wrap">
    <Ecompany name="公司简介" />
    <Eproduct name="产品展示" />
  </div>
</template>

<script>
// import banner1 from '@/assets/img/banner/banner1.png'
// import banner2 from '@/assets/img/banner/banner2.png'
// import banner3 from '@/assets/img/banner/banner3.png'
import Ecompany from '@/components/Ecompany'
import Eproduct from '@/components/Eproduct'
export default {
  components: { Ecompany, Eproduct },
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
</style>