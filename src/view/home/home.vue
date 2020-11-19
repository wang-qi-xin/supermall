<template>
  <div id="home"> 
    <!-- 顶栏       -->   
        <nav-bar id="bar">
              <div slot="left">《</div>
             <div slot="center">购物街</div>
        </nav-bar>
        <!-- 轮播图 -->
        <swiper id="swiper" :banner="banners"></swiper>
        <!-- recommend -->
        <recommend id="recommend" :recommend="recommend"/>
</div> 
</template>

<script>

const NavBar = () => import('components/common/navbar/NavBar.vue')
const swiper = () => import('./child/swiper.vue')
const recommend = () => import('./child/recommend.vue')


import {getHomeData} from 'network/home.js'

export default {
  name: 'Home',
  data() {
    return {
      banners: [],
      recommend: []
    }
  },
  components: {
    NavBar,
    swiper,
    recommend

  },
  created() {
    getHomeData().then(res => {
      // console.log(res)
      this.banners = res.data.banner.list
      this.recommend = res.data.recommend.list
    })
  }
}
</script>

<style>

#bar {
  background-color:  #d84848;
}


</style>
