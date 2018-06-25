<template>
  <div>
    <Top></Top>
    <TopBar></TopBar>
    <Nav></Nav>
    <HomeSub></HomeSub>
    <Goods></Goods>
  </div>
</template>

<script>
import Top from './components/top/Top.vue'
import TopBar from './components/bar/TopBar.vue'
import Nav from './components/nav/Nav.vue'
import HomeSub from './components/homeSub/HomeSub.vue'
import Goods from './components/goods/Goods.vue'

export default {
  components:{
    Top,
    TopBar,
    Nav,
    HomeSub,
    Goods
  }
}
</script>

<style>
*{
  font-size: 12px;
  font-family: Helvetica, Arial, "Microsoft Yahei", "Hiragino Sans GB", "Heiti SC", "WenQuanYi Micro Hei", sans-serif;
}
body{
  min-width: 1226px;
}
</style>
