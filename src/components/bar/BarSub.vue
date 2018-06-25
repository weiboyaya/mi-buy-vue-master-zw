<template>
    <div class="bar-sub">
        <ul class="bar-sub-ul">
            <li v-for="data in datas" :name="data.key" 
            class="bar-sub-li" @mouseover="showInfo(data)" 
            @mouseout="hideInfo()"
            >
            <a class="bar-sub-name" :href="data.url" target="_blank">{{data.name}}</a>
            <div v-if="data.key==currentKey&&data.key!='community'&&data.key!='service'?true:false" id="subInfo" @mouseover="showInfo(data)" @mouseout="hideInfo()">
                <ul class="info-ul">
                    <li v-for="d in data.infos" class="info-li">
                        <div class="info-container">
                            <div class="info-pic-div">
                                <img :src="d.pic"  class="info-img"/>
                            </div>
                            <div class="info-name">{{d.name}}</div>
                            <div class="info-price">{{d.price}}</div>
                        </div>
                    
                    </li>
                </ul>
            </div>
            </li>
        </ul>
        
    </div>
</template>
<script>
export default {
    data(){
        return{
            datas:[{
                name:'小米手机',
                key:'mi',
                infos:[{
                    name:'小米Max',
                    price:'1299元起',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/maxdingbu!160x110.jpg'
                },{
                    name:'小米手机5',
                    price:'1499元起',
                    pic:'http://c1.mifile.cn/f/i/16/goods/nav/mi5!160x110.jpg'
                },{
                    name:'小米手机4c',
                    price:'1099元起',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mi4c!160x110.jpg'
                }]
            },{
                name:'红米',
                key:'hMi',
                infos:[{
                    name:'红米pro',
                    price:'1499元起',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/hongmipro-320!160x110.jpg'
                },{
                    name:'红米note3',
                    price:'899元起',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/hongmi3s!160x110.jpg'
                },{
                    name:'红米手机3S',
                    price:'699元起',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/note3!160x110.jpg'
                },{
                    name:'红米手机3',
                    price:'699元起',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/hongmi3!160x110.jpg'
                },{
                    name:'红米手机3X',
                    price:'799元',
                    pic:'http://c1.mifile.cn/f/i/g/doodle/320-220!160x110.jpg'
                }]
            },{
                name:'平板·笔记本',
                key:'pad',
                infos:[{
                    name:'小米平板2 16GB',
                    price:'999元',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/hongmipro-320!160x110.jpg'
                },{
                    name:'小米平板2 64GB',
                    price:'1299元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mipad2-64!160x110.jpg'
                },{
                    name:'小米平板2 64GB Windows版',
                    price:'1299元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mipad2-64-win!160x110.jpg'
                },{
                    name:'小米笔记本Air 12.5',
                    price:'3499元',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/bijiben32012.5!160x110.jpg'
                },{
                    name:'小米笔记本Air 13.3',
                    price:'4999元',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben320!160x110.jpg'
                }]
            },{
                name:'电视',
                key:'TV',
                infos:[{
                    name:'小米电视3S 43英寸',
                    price:'1499元',
                    pic:'http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-43!160x110.jpg'
                },{
                    name:'小米电视3S 48英寸',
                    price:'1999元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mitv3s48!160x110.jpg'
                },{
                    name:'小米电视3 55英寸',
                    price:'3299元起',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mitv355!160x110.jpg'
                },{
                    name:'小米电视3 60英寸',
                    price:'3499元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mitv3-60!160x110.jpg'
                },{
                    name:'小米电视3S 65英寸 曲面',
                    price:'8999元',
                    pic:'http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-65!160x110.jpg'
                },{
                    name:'小米电视3 70英寸',
                    price:'8999元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mitv70!160x110.jpg'
                }]
            },{
                name:'盒子·影音',
                key:'box',
                infos:[{
                    name:'小米盒子mini版',
                    price:'179元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/hezimini.png'
                },{
                    name:'小米盒子3',
                    price:'249元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/hezi3.png'
                },{
                    name:'小米盒子3 增强版',
                    price:'399元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/hezi3s!160x110.jpg'
                },{
                    name:'小米电视主机',
                    price:'999元',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/zhuji!160x110.jpg'
                },{
                    name:'小米家庭音响 金属版',
                    price:'899元',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/jinshuban!160x110.jpg'
                },{
                    name:'小米家庭音响 标准版',
                    price:'699元',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/putonban!160x110.jpg'
                }]
            },{
                name:'路由',
                key:'router',
                infos:[{
                    name:'全新小米路由器',
                    price:'699元起',
                    pic:'http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-43!160x110.jpg'
                },{
                    name:'小米路由器 3',
                    price:'149元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/miwifi-3!160x110.jpg'
                },{
                    name:'小米路由器 mini',
                    price:'119元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/miwifimini!160x110.jpg'
                },{
                    name:'小米路由器 3C',
                    price:'99元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/mitv3-60!160x110.jpg'
                },{
                    name:'小米路由器 青春版',
                    price:'69元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/miwifilite!160x110.jpg'
                },{
                    name:'小米WiFi放大器',
                    price:'35元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/wifiExtension!160x110.jpg'
                }]
            },{
                name:'智能硬件',
                key:'Hardware',
                infos:[{
                    name:'九号平衡车',
                    price:'1999元',
                    pic:'http://c1.mifile.cn/f/i/15/goods/nav/scooter!160x110.jpg'
                },{
                    name:'小米净水器',
                    price:'1299元起',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/water2!160x110.jpg'
                },{
                    name:'米家压力IH电饭煲',
                    price:'999元',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/dianfanbao!160x110.jpg'
                },{
                    name:'小米空气净化器 2',
                    price:'649元',
                    pic:'http://c1.mifile.cn/f/i/16/goods/nav/air2!160x110.jpg'
                },{
                    name:'智能摄像机',
                    price:'149元起',
                    pic:'http://c1.mifile.cn/f/i/g/doodle/zhinengyingjian!160x110.jpg'
                }]
            },{
                name:'服务',
                key:'service',
                url:'http://www.mi.com/service/'
            },{
                name:'社区',
                key:'community',
                url:'http://www.xiaomi.cn'
            }],
            currentKey:'',
            infos:[]

        }
    },
    methods:{
        showInfo:function(data){
            this.currentKey=data?data.key:'';
            this.infos=data?data.infos:[];
        },
        hideInfo:function(){
           this.currentKey='';
           this.infos=[]; 
        }
    }
}
</script>
<style>
.bar-sub{
    width: auto;
    height: 100px;
    line-height: 100px;
}
.bar-sub-ul{
    list-style: none;
    margin: 0;
    padding: 0;
}
.bar-sub-li{
    float: left;
    margin-left: 20px;
    height: 100px;
}
.bar-sub-name{
    font-size: 16px;
    text-decoration: none;
    color: black;
}
.bar-sub-name:hover{
    cursor: pointer;
    color:#FF6700;
    font-size: 16px;
}
#subInfo{
    position: absolute;
	top: 90px;
    left: -6%;
    right: -7%;
    min-width: 1226px;
    height: 240px;
    margin: 0 ;
    box-shadow: 1px 1px 5px #ccc;
    cursor: pointer;
    z-index: 10;
    background: #fff;
}
.info-ul{
    list-style: none;
    text-align: center;
}
.info-li{
    float: left;
    height: 240px;
}
.info-container{
    margin: 30px 30px 0 0px;
    text-align: center;
    height: 240px;
}
.info-pic-div{
    padding-right: 30px;
    box-shadow: 1px 0 0 #ccc;
    height: 110px;
}
.info-img{
    width: 160px;
	height: 110px;
}
.info-name{
    height: 30px;
    margin-top: -20px;
    cursor:auto;
    padding-right: 30px;
}
.info-price{
    color:#FF6700;
    cursor:auto;
    padding-right: 30px;
}
</style>


