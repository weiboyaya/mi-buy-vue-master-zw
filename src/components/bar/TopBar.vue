<template>
    <div calss="top-bar">
        <div class="bar-container">
            <img class="icon-mi" src="../../assets/img/icon-mi.png" />
            <img class="icon-gif" src="../../assets/img/win.gif" />
            <BarSub></BarSub>
            <Search></Search>
        </div>
        
    </div>
</template>
<script>
import BarSub from '../bar/BarSub.vue'
import Search from '../bar/Search.vue'

export default {
    data(){
        return{

        }
    },
    components:{
        BarSub,
        Search
    }
    
}
</script>
<style>
.top-bar {
    width: 100%;
    height: 100px;
}
.bar-container{
    position: absolute;
    display: flex;
    margin: 0 auto;
    align-items: center;
    height: 100px;
    width: 90%;
    left: 5%;
}
.icon-mi {
    float: left;
    line-height: 100px;
    cursor: pointer;
}
.icon-gif{
    float: left;
    line-height: 100px;
    cursor: pointer;
}
</style>


