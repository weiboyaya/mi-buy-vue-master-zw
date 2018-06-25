<template>
    <div class="search">
        <input id="search-txt" type="text"/>
        <img id="search-btn">
        <div class="hot-item">
            <ul class="hot-item-ul">
                <li v-for="h in hot" :name="h.key" class="hot-item-li">{{h.name}}</li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            hot:[{
                name:'红米pro',
                key:'h-pro'
            },{
                name:'小米笔记本air',
                key:'h-air'
            }]
        }
    }
}
</script>
<style>
.search{
    width: auto;
    position: absolute;
    right: 0;
}
#search-txt{
     width:250px;
     height:45px;
     float: left;
     border:1px solid #e0e0e0;
     outline: none; 
}
#search-btn{
    background: url('../../assets/img/icon-search.png') center center no-repeat;
    background-size: 40%;
    background-repeat:no-repeat;
    width:50px;
    height:49px;
    float: left;
}
#search-btn:hover{
    background: url('../../assets/img/icon-search-white.png') center center no-repeat;
    background-size: 40%;
    background-repeat:no-repeat;
    width:50px;
    height:49px;
    float: left;
    background-color: #FF6700;
    cursor:pointer;
}
.hot-item-ul{
    list-style: none;
}
.hot-item{
    position: absolute;
    top:5px;
    right: 20%;
}
.hot-item-li{
    color:#757575;
    float: left;
    margin-left: 5px;
    border: 3px solid #eee;
    border-top-width: 0;
    background: #eee;
}
.hot-item-li:hover{
    color:#FFF;
    float: left;
    margin-left: 5px;
    border: 3px solid #FF6700;
    border-top-width: 0;
    background: #FF6700;
    cursor: pointer;
}
</style>


