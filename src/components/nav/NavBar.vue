<template>
   <div class="nav">
       <ul class="nav-title-ul">
           <li v-for="d in navData" :name="d.key" class="nav-title-li" @mouseover="showInfo(d)" @mouseout="hideInfo">
               <span class="nav-title-name">{{d.name}}</span>
               <div v-if="d.key==currentKey?true:false" class="nav-info">
                   <ul class="nav-info-ul" v-for="goods in filterInfos">
                       <li class="nav-info-li" v-for="info in goods">
                           <div class="nav-info-all">
                                <img :src="info.pic" class="nav-info-pic">
                                <div class="nav-info-name">{{info.name}}</div>
                                <span v-if="info.buyStatus" class="nav-info-status">选购</span>
                            </div>
                       </li>
                   </ul>
               </div>
           </li>
       </ul>
       <Carousel></Carousel>
    </div> 
</template>
<script>
import Carousel from '../../components/nav/Carousel.vue'

export default {
    data(){
        return{
            navData:[{
                name:'手机 电话卡',
                key:'phone',
                infos:[{
                    name:'小米手机5',
                    pic:'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40',
                    buyStatus:true
                },{
                    name:'小米Max',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/maxbar80.jpg?width=40&height=40',
                    buyStatus:true
                },{
                    name:'小米Note3',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/note3.jpg?width=40&height=40',
                    buyStatus:true
                },{
                    name:'红米手机3S',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/hm3s80x80.jpg?width=40&height=40',
                    buyStatus:true
                },{
                    name:'红米Pro',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/hongmi3.jpg?width=40&height=40',
                    buyStatus:true
                },{
                    name:'红米手机3',
                    pic:'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40',
                    buyStatus:true
                },{
                    name:'红米手机3X',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/3X80.jpg?width=40&height=40',
                    buyStatus:true
                },{
                    name:'合约机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/heyue.jpg?width=40&height=40',
                    buyStatus:false
                },{
                    name:'对比手机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/compare.jpg?width=40&height=40',
                    buyStatus:false
                },{
                    name:'小米移动 电话卡',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/mimobile.jpg?width=40&height=40',
                    buyStatus:false
                }]
            },{
                name:'笔记本 平板',
                key:'pad',
                infos:[{
                    name:'小米笔记本Air',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40',
                    buyStatus:true
                    },{
                    name:'小米平板2',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40',
                    buyStatus:true
                    },{
                    name:'USB-C转接器',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米笔记本内胆包',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            },{
                name:'电视 盒子',
                key:'tv',
                infos:[{
                    name:'小米电视 43英寸',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/4380side.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米电视 48英寸',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/mitv3s48.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米电视 55英寸',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/tv3-55.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米电视 60英寸',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/tv60.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米电视 65英寸',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/6580side.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米电视 70英寸',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/tv70.png?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米电视主机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/tvzj.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米盒子3 增强版',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/hezizengqiangban80side.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米盒子3',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/hezis.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米盒子 mini',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/hezimini.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米低音炮',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/diyinpao.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'蓝牙手柄',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/shb.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'家庭音响',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/zuheyinxiang80side.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'电视盒子配件',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/dianshipeijian.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            },{
                name:'路由器 智能硬件',
                key:'router',
                infos:[{
                    name:'小米VR眼镜玩具版',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/vr8080.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米无人机',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/wurenji80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米路由器',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/luyouqi-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'九号平衡车',
                    pic:'http://c1.mifile.cn/f/i/15/goods/list/scooter.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'米家压力IH电饭煲',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/dianfanbao-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'米家恒温电水壶',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/shuihu80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'电助力折叠自行车',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/zxc80-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'摄像机',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/xiaobai80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'净化器及滤芯',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/jinghuaqilvxin80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'净水器及滤芯',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/jingshuiqiandlvxin-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'血压计',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/xueyaji-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'智能灯',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/zhinengdeng-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'米兔智能故事机',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/gushiji80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'智能家庭组合',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/zhinengjiatingtaozhuang-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'手环及配件',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/shouhuan280.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'体重秤',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/scale.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'米兔儿童电话手表',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/shoubiao3-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'全部智能硬件',
                    pic:'http://c1.mifile.cn/f/i/g/doodle/znyjdaohang.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            },{
                name:'移动电源 电池 插线板',
                key:'power',
                infos:[{
                    name:'小米移动电源',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/dianyuan.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米插线板',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/powerscript.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'品牌移动电源',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/yidongdianyuan.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'移动电源附件',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/dianyuanfujian.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'电池',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/charger80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'充电器',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/chongdianqi-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'彩虹5号电池',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/5Battery1.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'彩虹7号电池',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/7Battery1.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            },{
                name:'耳机 音像',
                key:'headset',
                infos:[{
                    name:'小米头戴式耳机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/headphone.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米圈铁耳机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/quantie.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米胶囊耳机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/jiaonang80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米活塞耳机 基础版',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/jichuban-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米蓝牙耳机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/bluetoothheadset.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'品牌耳机',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/pinpai80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米蓝牙音箱',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/pocketaudio.png?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米随身蓝牙音箱',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/suishen-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小钢炮音箱 2',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/xiaogangpao2-hei-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小钢炮音箱 青春版',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/qignchungangpao-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米方盒子音箱',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/fanghezi.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'小米米兔音箱',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/mituyinx80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'网络收音机',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/radio80side.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'品牌音箱',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/pinpaiyinxiang.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            },{
                name:'保护套 贴膜',
                key:'protectors',
                infos:[{
                    name:'贴膜',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/tiemo.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'保护套/保护壳',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/baohu.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'后盖',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/hougai.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'背贴',
                    pic:'http://c1.mifile.cn/f/i/g/2015/video/tiezhi80.jpg?width=40&height=40',
                    buyStatus:false
                    }]            
            },{
                name:'线材 支架 存储卡',
                key:'card',
                infos:[{
                    name:'线材',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/xiancai.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'自拍杆',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/zipaigan.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'手机支架',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/zhijia.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'存储卡',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/cunchu.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            },{
                name:'箱包 服饰',
                key:'bags',
                infos:[{
                    name:'箱包',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/xiangbao-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'90分旅行箱',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/lvxingxiang.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'服饰',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/fuzhuang-80.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            },{
                name:'兔米 生活周边',
                key:'other',
                infos:[{
                    name:'米兔玩偶',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/mitu-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'鼠标垫',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/shubiaodian-80.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'生活周边',
                    pic:'http://c1.mifile.cn/f/i/15/goods/sidebar/zhoubian1.jpg?width=40&height=40',
                    buyStatus:false
                    },{
                    name:'《小米》杂志',
                    pic:'http://c1.mifile.cn/f/i/g/2015/cn-index/zazhi-80-80.jpg?width=40&height=40',
                    buyStatus:false
                    }]
            }],
            currentData:[],
            currentKey:''
        }
    },
    methods:{
        showInfo:function(data){
            this.currentKey=data.key;
            this.currentData=data.infos;
        },
        hideInfo:function(){
           this.currentKey='';
           this.currentData=[]; 
        }
    },
    computed:{
        filterInfos:function(){
            var goods=[];
            var good=[];
            var data=this.currentData;
            for(var i=0;i<data.length;i++){
                if(good.length<6){
                  good.push(data[i]);  
                }else{
                    goods.push(good);
                    good=[];
                    good.push(data[i]);
                }
            }
            good.length>0&& goods.push(good);
            return goods;
        }
    },
    components:{
        Carousel 
    }
}
</script>
<style>
.nav{
    width: 90%;
    height: auto;
    margin-left: 5%;
    position: absolute;
}
.nav-title-ul{
    width:20%;
    text-align: center;
    margin: 0;
    padding: 20px 0 20px 0;
    list-style: none;
    background: rgba(0, 0, 0, 0.3);
}
.nav-title-li{
    width:100%;
    height: 42px;
}
.nav-title-li:hover{
    width:100%;
    background:#FF6700;
    height: 42px;
}
.nav-title-name{
    font-size: 14px;
    color: #fff;
    line-height: 42px;
}
.nav-info{
    position: absolute;
    display: flex;
	flex-flow: row nowrap;
	justify-content: flex-start;
    top: 0;
    left: 20%;
    width: auto;
    height: 460px;
    box-shadow: 2px 2px 5px #ccc;
    background: white;
    margin: 0;
    padding: 0;
    z-index: 10;
}
.nav-info-ul{
    margin: 0;
    padding: 0;
    list-style: none;
}
.nav-info-li{
    height: 76.6px;
    width: 265px;
    line-height: 76.6px;
    cursor: pointer;
}
.nav-info-all{
    height: 76.6px;
    line-height: 76.6px;
}
.nav-info-pic{
    margin: 16.3px 0 0 30px;
    float: left;
}
.nav-info-name{
    float: left;
    margin-left: 10px;
}
.nav-info-name:hover{
    float: left;
    margin-left: 10px;
    color:#FF6700;
}
.nav-info-status{
    float: right;
    border: 1px solid #FF6700;
    color: #FF6700;
    height: 20px;
    line-height: 20px;
    width: 60px;
    margin: 28.3px 20px 0 0;
}
.nav-info-status:hover{
    float: right;
    border: 1px solid #FFF;
    height: 20px;
    line-height: 20px;
    width: 60px;
    margin: 28.3px 20px 0 0;
    background: #FF6700;
    color: #fff;
}
</style>

