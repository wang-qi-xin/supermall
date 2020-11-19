<template>
  
    <div id="tab-bar-flex" @click="itemClick">
      <div v-if="!isActive">
        <slot name="item-icon"></slot>
      </div>
      <div v-else>
        <slot name="item-icon-active"></slot>
      </div>
       <div :style="activeStyle"> <!--动态绑定样式计算属性 -->
        <slot name="item-text"></slot>
      </div>
      <!-- <img src="../../assets/imag/tabbar/home.svg" alt="">
      <div>首页</div> -->
    </div>
 
</template>

<script>
export default {
  name: 'TabBarItem',
  props: {
    path: String,
    activeColor: {
      type: String,
      default: "red",
      required: false
    }
  },
  data() {
    return {
      // isActive: false,
      // path: '/cart'
    }
  },
  computed: {
    isActive() { //判断是否处于激活，激活返回true
      return this.$route.path.indexOf(this.path) != -1  
    },
    activeStyle() {//如果激活状态，就添加样式
      return this.isActive?{color:this.activeColor}:{}
    }
  },
  methods: {
    // Active() {
    //   this.isActive = ! this.isActive
    // },
    itemClick() {
      if(this.$route.path != this.path){ //如果已经激活，就不执行操作
      this.$router.replace(this.path)
      // this.isActive = ! this.isActive
      }
    }
  },
}
</script>

<style scoped>


#tab-bar-flex {
  flex: 1;  /*//让所有弹性盒模型对象的子元素都有相同的长度，且忽略它们内部的内容 */
  text-align: center;  /**文字居中 */
  height: 49px;
}
#tab-bar-flex img{
  height: 24px;   /**图片大小 */
  width: 24px;
  margin-top: 3px;  /**图片往下3px */
  vertical-align: middle; 
  margin-bottom: 1px; /**图片下面默认的3px，会使得图片跟文字有间距 */
}

</style>
