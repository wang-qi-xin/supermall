<template>
  <div id="tab-bar">
    <slot></slot>
  </div>  
</template>

<script>
export default {
  name: 'TabBar'
}
</script>

<style scoped>
/* @import './assets/css/base.css';  //style里引用需要加@ */
#tab-bar{
   display: flex;  /*//让所有弹性盒模型对象的子元素都有相同的长度，且忽略它们内部的内容 */
  background-color: #f6f6f6;

  position: fixed;  /* 生成绝对定位的元素，相对于浏览器窗口进行定位。 */
  left: 0;
  right: 0;
  bottom: 0;

  box-shadow:0 -2px 8px red;  /**画渐变阴影 */
}

</style>
