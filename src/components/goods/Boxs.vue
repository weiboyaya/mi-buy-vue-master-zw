<template>
    <div class="boxs-container">
        <div class="boxs-head">
            <div class="boxs-title">智能硬件</div>
            <div class="boxs-checkAll">查看全部</div>
        </div>
        <div class="boxs-content">
            <div class="boxs-left">
                <img src="http://i3.mifile.cn/a4/124d82cc-cfce-44ab-b711-28b21be81683" />
            </div>
            <div class="boxs-right">
                <ul class="boxs-ul" v-for="box in getBoxs">
                    <li class="boxs-li" v-for="b in box">
                        <div :class="[b.flag,'boxs-label']">
                            {{b.label}}
                        </div>
                        <div class="boxs-img-content">
                            <img :src="b.pic" class="boxs-img">
                        </div>
                        <div class="boxs-name">
                            {{b.name}}
                        </div>
                        <div class="boxs-info">
                            {{b.info}}
                        </div>
                        <div class="boxs-price">
                            <span class="boxs-currentPrice">{{b.price}}</span>
                            <span class="boxs-costPrice">{{b.costPrice}}</span>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            boxs:[{
                name:'小米路由器3',
                info:'四天线设计，更安全更稳定',
                price:'149元',
                costPrice:'',
                pic:'http://i3.mifile.cn/a4/T1rQAgB7Av1RXrhCrK.jpg',
                flag:'free',
                label:'免邮费'
            },{
                name:'电助力折叠自行车',
                info:'力矩传感电助力，让城市出行轻松有缺',
                price:'149元',
                costPrice:'',
                pic:'http://i3.mifile.cn/a4/2b69b930-a2fd-4d09-a46a-8690cb79f764',
                flag:'new',
                label:'新品'
            },{
                name:'米兔智能故事机',
                info:'能说会道，宝宝的好玩伴',
                price:'199元',
                costPrice:'',
                pic:'http://i1.mifile.cn/a1/pms_1464615180.86261317!220x220.jpg',
                flag:'new',
                label:'新品'
            },{
                name:'小米净水器',
                info:'厨下式RO反渗透直出纯净水，包邮包安装',
                price:'1999元',
                costPrice:'',
                pic:'http://i3.mifile.cn/a4/T1zTK_Bbhv1RXrhCrK.jpg',
                flag:'',
                label:''
            },{
                name:'iHealth智能血压计(蓝牙版)',
                info:'送给父母的健康礼物 测血压仅需1步',
                price:'199元',
                costPrice:'',
                pic:'http://i1.mifile.cn/a1/T17FCQByWv1RXrhCrK!220x220.jpg',
                flag:'',
                label:''
            },{
                name:'米家压力IH电饭煲',
                info:'智能烹饪，3L容量',
                price:'999元',
                costPrice:'',
                pic:'http://i1.mifile.cn/a1/T1OVC_ByY_1RXrhCrK!220x220.jpg',
                flag:'',
                label:''
            },{
                name:'全系只能套装限时款',
                info:'开启你的智慧生活',
                price:'292元',
                costPrice:'325元',
                pic:'http://i1.mifile.cn/a1/pms_1470730028.12443689!220x220.jpg',
                flag:'sale',
                label:'享九折'
            },{
                name:'小米手环 光感版',
                info:'实时监测心率，科学运动',
                price:'99元',
                costPrice:'',
                pic:'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg',
                flag:'',
                label:''
            }]
        }
    },
    computed:{
        getBoxs:function(){
            var boxList=[];
            var box=[];
            for(var i=1;i<=this.boxs.length;i++){
                if(i%4==0){
                    box.push(this.boxs[i-1]);
                    boxList.push(box);
                    box=[];
                }else{
                    box.push(this.boxs[i-1]);
                }
            }
            box.length>0&&boxList.push(box);
            return boxList;
        }
    }
}
</script>
<style>
.boxs-container{
    position: absolute;
    width: 100%;
    height: auto;
    top:0;
    left: 0;
}
.boxs-head{
    height: 58px;
    line-height: 58px;
}
.boxs-title{
    font-size: 22px;
    float: left;
}
.boxs-checkAll{
    font-size: 16px;
    float: right;
}
.boxs-checkAll:hover{
    font-size: 16px;
    float: right;
    color:#FF6700;
    cursor: pointer;
}
.boxs-content{
    position: absolute;
    top: 58px;
    left: 0;
    height: 614px;
    width: 100%;
}
.boxs-left{
    width: 234px;
    height: 614px;
}
.boxs-left:hover{
    width: 234px;
    height: auto;
    box-shadow: 5px 5px 10px #ccc;
    margin-top: -2px;
    transition:all 0.3s;
    cursor: pointer;
}
.boxs-right{
    position: absolute;
    top:0;
    left:234px;
    width: calc(100% - 234px);
    height: 614px;
}
.boxs-ul{
    float: left;
    margin: 0;
    padding: 0;
    list-style: none;
    width: 100%;
    height: 307px;
}
.boxs-li{
     float: left;
     width:24%;
     height:300px;
     margin-left: calc(1% - 2px);
     border: 1px solid #ccc;
}
.boxs-li:hover{
     float: left;
     width:24%;
     height:300px;
     margin-left: calc(1% - 2px);
     border: 1px solid #ccc;
     margin-top: -2px;
     transition:all 0.3s;
     box-shadow: 5px 5px 10px #ccc;
}
.boxs-label{
    position: absolute;
    text-align: center;
    margin-left: calc(12% - 32px );
    width: 64px;
    height: 20px;
    line-height: 20px;
}
.new{
    color:white;
    background: #83c44e;
}
.free{
    color:white;
    background: #ffac13;
}
.sale{
    color:white;
    background: #e53935;
}
.boxs-img{
    margin-top: 20px;
    width: 160px;
    height: 160px;
    cursor: pointer;
}
.boxs-img-content{
    text-align: center;
}
.boxs-name{
    text-align: center;
    font-size: 14px;
    margin-top: 15px;
    cursor: pointer;
}
.boxs-info{
    text-align: center;
    margin-top: 15px;
    color: #ccc;
    overflow: hidden;
    text-overflow:ellipsis;
    white-space: nowrap; 
}
.boxs-price{
    text-align: center;
    margin-top: 15px;
}
.boxs-costPrice{
   color:#ccc;
   text-decoration:line-through;
   font-size: 14px;
}
.boxs-currentPrice{
    color: #FF6700;
    font-size: 14px;
}
</style>
