<template>
<div class="tabbaritem">
    <div :style="{'color':activedColor}" @click="itemClick"><slot></slot></div>
</div>
</template>

<script>
export default {
    name:'TabbarItem',
    props:{
        path:'',
        activeColor:{
            type:String,
            default:'pink'
        }
    },
    data(){
        return{
            
        }
    },
    computed:{
        isActive(){
            // return this.$router.path.indexof('/') == 1
            let router_path = this.$route.path
            return router_path ==this.path
        },
        activedColor(){
            return this.isActive?this.activeColor:''
        }
    },
    methods:{
        itemClick(){
            this.$router.replace(this.path)
        }
    }
}
</script>

<style>
.tabbaritem{
    height: 34px;
    flex: auto;
}
</style>