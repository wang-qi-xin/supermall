<template>
    <!-- 轮播图 -->   
    <div class="recommend">
        <div v-for="(item,index) in recommend" class="recommend-item" :key="index">
            <a :href="item.link">
                <img :src="item.image" alt="">
                <div>{{item.title}}</div>
            </a>
        </div>

    </div>

</template>

<script>


export default {
  name: 'Home',
  props: {
      recommend: {
          type: String,
          default: []
      }
  },
  data() {
    return {   
    }
  },

}
</script>

<style>
    .recommend {
        /* margin-top: 240px; */
        position: fixed;
        width: 100%;
        left: 0;
        right: 0;
        top: 250px;

        margin-bottom: 20px;
        display: flex;
        width: 100%;
        text-align: center;
        font-size: 12px;

        border-bottom: 8px solid #eee;
    }
    .recommend-item {
        flex: 1;
        margin-bottom: 10px;
    }
    
    .recommend-item img {
        width: 65px;
        height: 65px;
        margin-bottom: 6px;
    }
</style>
