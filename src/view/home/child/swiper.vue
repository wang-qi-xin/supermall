<template>
    <!-- 轮播图 -->   
      <swiper class="swiper">
        <swiper-item v-for="(item,index) in banner" :key="index">
          <a :href="item.link">
            <img :src="item.image" alt="">
          </a>
        </swiper-item>
      </swiper>

</template>

<script>

import {Swiper,SwiperItem} from 'components/common/swiper/index.js'

export default {
  name: 'Home',
  props: {
      banner: {
          type: String,
          default: []
      }
  },
  data() {
    return {   
    }
  },
  components: {
    Swiper,
    SwiperItem,
  },

}
</script>

<style>
.swiper {
  height: 100px;
  line-height: 100px;
  
   position: fixed; 
        width: 100%;
        left: 0;
        right: 0;
        top: 44px;
}

</style>
