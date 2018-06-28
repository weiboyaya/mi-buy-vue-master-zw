<template>
    <div class="recommend-container">
        <div class="recommend-head">
            <div class="recommend-head-title">为你推荐</div>
            <div class="recommend-head-menu">
                <div :class="leftMenuClass" @click="goTo(1)"></div>
                <div :class="rightMenuClass" @click="goTo(10)"></div>
            </div>
        </div>
        <div class="recommend-content">
            <!--<transition name="fade">-->
                <ul :class="ulClass">
                    <li class="recommend-content-li" v-for="data in datas">
                        <div class="recommend-img-content">
                            <img :src="data.pic" class="recommend-img">
                        </div>
                        <div class="recommend-name">
                            {{data.name}}
                        </div>
                        <div class="recommend-price">
                            {{data.price}}
                        </div>
                        <div class="recommend-rank">
                            {{data.rank}}
                        </div>
                    </li>
                </ul>
            <!--</transition>-->
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            datas:[{    
                        id:'1',
                        name:'小米AI音箱',
                        price:'299元',
                        pic:'http://i1.mifile.cn/a1/pms_1522666970.27937468.jpg?width=150&height=150',
                        rank:'4.9万人评价',
                        evaluate:'狂拽炫酷吊炸天，功能慢慢摸索中！',
                        origin:'来自于 680216907 的评价'
            },{
                        id:'2',
                        name:'小米小爱音箱mini',
                        price:'169元',
                        pic:'http://i1.mifile.cn/a1/pms_1524571235.37826274.jpg?width=150&height=150',
                        rank:'8041人评价',
                        evaluate:'',
                        origin:''
                    },{
                        id:'3',
                        name:'小米移动电源5000mAh',
                        price:'49元',
                        pic:'http://i1.mifile.cn/a1/T1pZbvBTET1RXrhCrK!220x220.jpg',
                        rank:'10.9万人评价',
                        evaluate:'',
                        origin:''
                    },{
                        id:'4',
                        name:'小米电源线收纳盒',
                        price:'49元',
                        pic:'http://i1.mifile.cn/a1/T1eKdgB4xv1RXrhCrK!220x220.jpg',
                        rank:'',
                        evaluate:'',
                        origin:''
                    },{
                        id:'5',
                        name:'小米6X 极简保护壳',
                        price:'29元',
                        pic:'http://i1.mifile.cn/a1/pms_1524466977.94886383.jpg?width=150&height=150',
                        rank:'513人评价',
                        evaluate:'',
                        origin:''
                    },{
                        id:'6',
                        name:'Mi MIX 2S 硅胶保护套',
                        price:'59元',
                        pic:'http://i1.mifile.cn/a1/pms_1523354403.31383469.png?width=150&height=150',
                        rank:'529人评价',
                        evaluate:'',
                        origin:''
                    },{
                        id:'7',
                        name:'红米note4X 智能显示保护套',
                        price:'39元',
                        pic:'http://i1.mifile.cn/a1/pms_1488522312.21011606!220x220.jpg',
                        rank:'3463人评价',
                        evaluate:'',
                        origin:''
                    },{
                        id:'8',
                        name:'红米 5 Plus 极简防摔保护套 黑色',
                        price:'19元',
                        pic:'http://i1.mifile.cn/a1/pms_1512957185.6636673!220x220.jpg',
                        rank:'1541人评价',
                        evaluate:'',
                        origin:''
                    },{
                        id:'9',
                        name:'红米S2 标准高透膜',
                        price:'10元',
                        pic:'http://i1.mifile.cn/a1/pms_1526349330.12883818!220x220.jpg',
                        rank:'14人评价',
                        evaluate:'',
                        origin:''
                    },{
                        id:'10',
                        name:'小米Max2 高透保护膜',
                        price:'10元',
                        pic:'http://i1.mifile.cn/a1/pms_1496238415.93753872!220x220.jpg',
                        rank:'4971人评价',
                        evaluate:'',
                        origin:''
                    }],
                    ulClass:'recommend-content-ul',
                    leftMenuClass:'recommend-head-menu-left',
                    rightMenuClass:'recommend-head-menu-right-hover'
        }
    },
    methods:{
        goTo:function(val){
            if(val==1){
                this.leftMenuClass='recommend-head-menu-left-hover';
                this.rightMenuClass='recommend-head-menu-right';
                this.ulClass='recommend-content-ul-hover';
            }else{
                this.leftMenuClass='recommend-head-menu-left';
                this.rightMenuClass='recommend-head-menu-right-hover';
                this.ulClass='recommend-content-ul';
            }
            
        }
    }
}
</script>
<style>
.recommend-container{
    position: absolute;
    top:3593px;
    width: 90%;
    height: 368px;
    left: 5%;
    margin-top: 26px;
}
.recommend-head{
    position: absolute;
    height: 58px;
    width: 100%;
}
.recommend-head-title{
    font-size: 22px;
    float: left;
    line-height: 58px;
}
.recommend-head-menu{
    float: right;
    line-height: 58px;
    width: auto;
}

.recommend-head-menu-left{
    width: 30px;
    height: 30px;
    background: url("../../assets/img/icon-left.png") center no-repeat;
    float: right;
    border: 1px solid #ccc;
}
.recommend-head-menu-left:hover{
    width: 30px;
    height: 30px;
    background: url("../../assets/img/icon-left-hover.png") center no-repeat;
    float: right;
    border: 1px solid #FF6700;
    cursor: pointer;
}
.recommend-head-menu-left-hover{
    width: 30px;
    height: 30px;
    background: url("../../assets/img/icon-left-hover.png") center no-repeat;
    float: right;
    border: 1px solid #FF6700;
    cursor: pointer;
}
.recommend-head-menu-right{
    width: 30px;
    height: 30px;
    background: url("../../assets/img/icon-right.png") center no-repeat;
    float: right;
    border: 1px solid #ccc;
}
.recommend-head-menu-right:hover{
    width: 30px;
    height: 30px;
    background: url("../../assets/img/icon-right-hover.png") center no-repeat;
    float: right;
    border: 1px solid #FF6700;
    cursor: pointer;
}
.recommend-head-menu-right-hover{
    width: 30px;
    height: 30px;
    background: url("../../assets/img/icon-right-hover.png") center no-repeat;
    float: right;
    border: 1px solid #FF6700;
    cursor: pointer;
}
.recommend-content{
    position: absolute;
    top: 58px;
    left: 0;
    width: 100%;
    height: 310px;
    overflow: hidden;
}
.recommend-content-ul{
    position: absolute;
    transition: all 1s;
    margin: 0;
    padding: 0;
    list-style: none;
    width: 2452px;
    margin-left:0px;
    height: 310px;
}
.recommend-content-ul-hover{
    position: absolute;
    transition: all 1s;
    margin: 0;
    padding: 0;
    list-style: none;
    width: 2452px;
    margin-left: -1210px;
    height: 310px;
}
.recommend-content-li{
    float: left;
    width: 234px;
    height: 300px;
    margin: 5px 7px 5px 0;
    border: 1px solid #ccc;
    cursor: pointer;
}
.recommend-content-li:hover{
    float: left;
    width: 234px;
    height: 300px;
    margin: 5px 7px 5px 0;
    border: 1px solid #ccc;
    cursor: pointer;
    margin-top: -0.1px;
    transition: all 0.3s;
    box-shadow: 5px 5px 5px #ccc;
}
.recommend-img-content{
    text-align: center;
    width: 234px;
    height: 150px;
    margin-top: 40px;
}
.recommend-img{
    width: 150px;
    height: 150px;
}
.recommend-name{
    text-align: center;
    font-size: 14px;
    margin-top: 10px;
}
.recommend-price{
    text-align: center;
    font-size: 14px;
    color: #FF6700;
    margin-top: 10px;
}
.recommend-rank{
    text-align: center;
    color: #ccc;
    margin-top: 10px;
}
/*.fade-enter-active, .fade-leave-active {
    transition: all 1s ease;
}
.fade-enter, .fade-leave-to{
    transform: translateX(10px);
    opacity: 0;
}*/
  
</style>
