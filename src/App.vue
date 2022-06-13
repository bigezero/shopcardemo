<template>
  <div>
    <Header background="#ee1771" color="#fff" title="购物车案例"></Header>
    <div class="main">
      <Goods v-for="item in list" :key="item.id" :obj="item"></Goods>
    </div>
    <Footer></Footer>
  </div>
</template>

<script>
import Footer from "./components/Footer.vue";
import Goods from "./components/Goods.vue";
import Header from "./components/Header.vue";

export default {
  components: {
    Footer,
    Goods,
    Header,
  },
  data(){
    return {
      list:[]
    }
  },
  created(){
    this.$axios({
      url:'/api/cart'
    }).then(res=>{
      this.list = res.data.list
    })
  }
}
</script>

<style scoped>
.main{
  margin-top: 45px;
  margin-bottom: 50px;
}
</style>