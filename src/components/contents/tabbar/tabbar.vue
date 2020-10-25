<template>
<div class="tabbar">
  <TabbarItem path='/' activeColor='blue'>首页</TabbarItem>
  <TabbarItem path='/category'>分类</TabbarItem>
  <TabbarItem path='/cart'>购物车</TabbarItem>
  <TabbarItem path='/profile'>我的</TabbarItem>
</div>
</template>

<script>
import TabbarItem from '@/components/contents/tabbar/tabbaritem.vue'
export default {
    name:'Tabbar',
    components:{
        TabbarItem
    }

}
</script>

<style>
    .tabbar{
        position: fixed;
        bottom: 0px;
        left: 0px;
        display: flex;

    }
</style>