<template>
  <div id="app">
    <router-view/>
    <Tabbar/>
  </div>
</template>
<script>
import Tabbar from '@/components/contents/tabbar/tabbar.vue'
export default {
  name:'app',
  components:{
    Tabbar
  }

}
</script>

<style>
@import url(assets/css/base.css);
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
