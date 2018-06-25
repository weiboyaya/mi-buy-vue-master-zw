<template>
  <div class="top-index">
      <div class="top-container">
        <ul class="top-index-ul">
            <li v-for="data in indexData" class="top-index-ul-li">
                <a :href="data.dataSource" target="_blank" class="top-index-source space">{{data.name}}</a>
                <span class="top-index-split space">|</span>
            </li>
            
        </ul>
        <div :class="show?'top-shop-car top-shop-car-hover':'top-shop-car' " @mouseover="showShopCar" @mouseout="hideShopCar">
            <span>购物车({{items}})</span>
        </div>
        <div class="top-index-login">
            <a :href="datas[0].dataSource" class="top-index-source top-index-hover">{{datas[0].name}}</a>
            <span  class="top-index-split">|</span>
            <a :href="datas[1].dataSource" class="top-index-source top-index-hover">{{datas[1].name}}</a>
        </div>
      </div>
      <div v-if="show" id="shopCar" @mouseover="showShopCar" @mouseout="hideShopCar">
            <span>购物车中还没有商品，赶快选购吧</span>
        </div>
  </div>  
</template>
<script>

export default {
    data(){
        return{
            indexData:[{
                name:'小米商城',
                dataSource:'https://www.mi.com/index.html'
            },{
                name:'MIUI',
                dataSource:'http://www.miui.com/'
            },{
                name:'米聊',
                dataSource:'http://www.miliao.com/'
            },{
                name:'游戏',
                dataSource:'http://game.xiaomi.com/'
            },{
                name:'多看阅读',
                dataSource:'http://www.duokan.com/'
            },{
                name:'云服务',
                dataSource:'https://i.mi.com/'
            },{
                name:'小米网移动版',
                dataSource:'http://www.mi.com/c/appdownload/'
            },{
                name:'问题反馈',
                dataSource:'http://static.mi.com/feedback/'
            },{
                name:'Select Region',
                dataSource:'http://www.mi.com/index.html'
            }],
            datas:[{
               name:'登录',
               dataSource:'http://order.mi.com/site/login?redirectUrl=http://www.mi.com/index.html'
            },{
               name:'注册',
               dataSource:'https://account.xiaomi.com/pass/register'
            }],
            items:0,
            show:false
        }
    },
    methods:{
        showShopCar:function(){
            this.show=true;
        },
        hideShopCar:function(){
            this.show=false;
        }
    },
    components:{
       
    }    
}
</script>
<style>
.top-index{
    height: 40px;
    background:#333333;
    line-height: 40px;
    color:#B0B0B0;
}
.top-container{
    position: absolute;
    width:90%;
    height: 40px;
    margin-left: 5%
}
.top-index-ul{
    list-style: none;
    margin: 0;
    padding: 0;
}
.top-index-ul-li{
    float: left;
}
.top-index-source {
     color:#B0B0B0;
     text-decoration: none;
}
.top-index-split{
    color:#B0B0B0;
   
}
.space{
    margin-left: 5px;
}
.top-index-login{
    float: right;
    margin-right: 20px;
}
.top-index-hover:hover{
    color:white;
}
.top-shop-car{
    float: right;
    width: 120px;
    text-align: center;
    cursor: pointer;
}
.top-shop-car-hover{
    background: white;
    color:#FF6700;
}
.top-shop-car:hover{
    background: white;
    color:#FF6700;
}
#shopCar{
    position:absolute;
	right:5%;
	top: 49px;
    width: 316px;
    height: 96px;
    line-height: 96px;
	text-align: center;
	color: #b0b0b0;
	background: #fff;
	box-shadow: 0 0 5px #ccc;
    z-index: 10;
    overflow: hidden;
    cursor: pointer;
}
</style>


