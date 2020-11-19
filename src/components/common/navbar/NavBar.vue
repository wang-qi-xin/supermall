<template>
    <div class="nav-bar">
        <div class="left">
            <slot name="left"></slot>
        </div>
        <div class="center">
            <slot name="center"></slot>
        </div>
        <div class="right">
            <slot name="right"></slot>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavBar'
}
</script>

<style>
    .nav-bar {
        display: flex;
        line-height: 44px;
        height: 44px;
        text-align: center;
        box-shadow:0 -2px 8px red;  /**画渐变阴影 */

        /* 生成绝对定位的元素，相对于浏览器窗口进行定位。 */
        position: fixed; 
        width: 100%;
        left: 0;
        right: 0;
        top: 0;
    }

    .left,.right {
        width: 60px;
        /* background-color: red; */
    }

    .center {
        flex: 1;
        /* background-color: blue; */
    }
</style>