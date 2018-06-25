<template>
    <div class="home-sub">
        <Span4></Span4>
        <homeSpan></homeSpan>
    </div>
</template>
<script>

import Span4 from '../../components/homeSub/Span4.vue'
import homeSpan from '../../components/homeSub/homeSpan.vue'

export default {
    components:{
        Span4,
        homeSpan
    }
}
</script>
<style>
.home-sub{
    position: absolute;
    width: 90%;
    height: 170px;
    top:600px;
    left: 5%;
    margin-top: 7px;
    margin-bottom: 26px;
}
</style>

