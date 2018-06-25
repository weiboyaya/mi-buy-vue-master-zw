<template>
    <div id="nav">
        <NavBar></NavBar>
    </div>
</template>
<script>
import NavBar from '../../components/nav/NavBar.vue'


export default {
    components:{
       NavBar
    }
}
</script>
<style>
#nav{
    position: absolute;
    top: 140px;
    left: 0;
    width: 100%;
    height: 460px;
}
</style>


