<template>
  <div class="my-header" :style="{backgroundColor:background,color}">{{title}}</div>
</template>

<script>
//自定义Header
//1.分析那些可以自定义（背景色，文字颜色，文字内容）
export default {
  props:{
    background:String,
    color:{
      type:String,
      default:"#fff" //当前默认值
    },
    title:{
      type:String,
      required:true
    }
  }
}
</script>

<style lang="less" scoped>
  .my-header {
    height: 45px;
    line-height: 45px;
    text-align: center;
    background-color: #ee1771;
    color: #fff;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 2;
  }
</style>