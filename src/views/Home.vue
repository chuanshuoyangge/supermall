<template>
  <div class="home">
    <Navbar class="navbar">
      <template v-slot:left>返回</template>
      <template v-slot:center>主页</template>
      <template v-slot:right>首页</template>
    </Navbar>
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide v-for="(item,index) in banner.list" :key="index">
          <a :link='item.link'><img :src="item.image"></a>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
     </swiper>
     <Recommend :recommend='recommend.list'/>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from '@/components/contents/navbar/navbar.vue'
import {getHomeData} from '../network/home.js'
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
import 'swiper/swiper-bundle.css'
import Recommend from './home/recommend'

export default {
  name: 'Home',
  components: {
    Navbar,
    Swiper,
    SwiperSlide,
    Recommend
  },
  data(){
    return{
      banner:[],
      recommend:[],
      swiperOptions: {
        pagination: {
          el: '.swiper-pagination',
          type: 'bullets',
        },
        loop:true,
        effect:'cube',
        // on: {
        //   resize: function(){
        //     this.params.width = window.innerWidth;
        //     this.update();
        //   },
        // }
        // // width: window.innerWidth,
        // // width:400
        //  // Some Swiper option/callback...
       }
     }
  },
  computed:{
    swiper() {
        return this.$refs.mySwiper.$swiper
      }
  },
  mounted() {
      console.log('Current Swiper instance object', this.swiper)
      this.swiper.slideTo(3, 1000, false)
  },
  created(){
    getHomeData()
    .then(res=>{
      console.log(res.data.data.recommend)
      this.banner=res.data.data.banner;
      this.recommend=res.data.data.recommend      
    })
    .catch(err=>{
      console.log(err)
    })
  }
}
</script>
<style>
  .navbar{
    display: flex;
  }
  .navbar div:nth-child(1){
    width: 60px;
  }
  .navbar div:nth-child(2){
    flex: auto;
  }
  .navbar div:nth-child(3){
    width: 60px;
  }
  .swiper-container{
    width: 100%;
  }
  .swiper-slide{
    width: 100%;
  }
</style>
