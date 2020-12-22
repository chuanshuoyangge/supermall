<template>
    <div class="navbar">
        <div><slot name="left"></slot></div>
        <div><slot name="center"></slot></div>
        <div><slot name="right"></slot></div>
    </div>
</template>

<script>
export default {
    name:'Navbar'
}
</script>

<style>
    .navbar{
        background-color: antiquewhite;
        width: 100%;
    }
</style>