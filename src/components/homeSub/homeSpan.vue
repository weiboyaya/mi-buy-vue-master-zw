<template>
     <div class="home-sub-spans">
        <ul class="home-sub-spans-ul">
            <li v-for="d in datas" class="home-sub-spans-li">
                <img :src="d.path" class="home-sub-spans-img"/>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data(){
        return{
            datas:[{
                path:'http://i1.mifile.cn/a4/xmad_15296329058414_naXxe.jpg'
            },{
                path:'http://i1.mifile.cn/a4/xmad_15286869169634_yjGTF.jpg'
            },{
                path:'http://i1.mifile.cn/a4/xmad_15294897230285_fVNvp.png'
            }]
        }
    }
}
</script>
<style>
.home-sub-spans{
    position: absolute;
    width:80%;
    top:0;
    left:20%;
}
.home-sub-spans-ul{
    list-style: none;
    margin: 0;
    padding: 0;
}
.home-sub-spans-li{
    float: left;
    width: calc(33.3% - 7px);
    height: 170px;
    margin-left: 7px;
    cursor: pointer;
    border: 10px 10px 5px #ccc;
}
.home-sub-spans-li:hover{
    float: left;
    width: calc(33.3% - 7px);
    height: 170px;
    margin-left: 7px;
    cursor: pointer;
    box-shadow: 2px 5px 5px #ccc;
}
.home-sub-spans-img{
    width: 100%;
    height: 170px;
}

</style>


