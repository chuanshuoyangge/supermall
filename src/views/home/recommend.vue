<template>
  <div class="recommend">
      <div v-for="(item,index) in recommend" :key="index" class="recommend-item">
          <img :src="item.image">
          <p>{{item.title}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name:'Recommend',
    props:{
        recommend:Array
    }

}
</script>

<style>
    .recommend{
        display: flex;
        width: 100%;
        flex-wrap: wrap;
    }
    .recommend-item{
        flex: auto;
        max-width: 200px;
    }
    .recommend-item img{
        max-width: 200px;
    }

</style>