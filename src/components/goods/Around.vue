<template>
    <div class="around-container">
        <div class="around-head">
            <div class="around-menu">
                <ul class="around-menu-ul">
                    <li :class=" key==menu.key?'around-menu-li-hover':'around-menu-li'" v-for=" menu in roundData1.menu"
                     @click="changeItems(menu.key)" @mouseover="changeItems(menu.key)">
                        {{menu.name}}
                    </li>
                </ul>
            </div>
            <div class="around-title">
                {{roundData1.title}}
            </div>
        </div>
        <div class="around-content">
            <div class="around-left">
                <img class="around-left-img1" :src="roundData1.demoPic[0]" />
                <img class="around-left-img2" :src="roundData1.demoPic[1]" />
            </div>
            <div class="around-right">
                <ul class="around-right-ul">
                    <li class="around-right-li" v-for=" a1 in getFirstList ">
                        <div class="around-img-content">
                            <img :src="a1.pic" class="around-right-img">
                        </div>
                        <div class="around-right-name">
                            {{a1.name}}
                        </div>
                        <div class="around-right-price">
                            {{a1.price}}
                        </div>
                        <div class="around-right-rank">
                            {{a1.rank}}
                        </div>
                    </li>
                </ul>
                <ul class="around-right-ul">
                    <li class="around-right-li" v-for=" a2 in getSecondList ">
                        <div class="around-img-content">
                            <img :src="a2.pic" class="around-right-img">
                        </div>
                        <div class="around-right-name">
                            {{a2.name}}
                        </div>
                        <div class="around-right-price">
                            {{a2.price}}
                        </div>
                        <div class="around-right-rank">
                            {{a2.rank}}
                        </div>
                    </li>
                </ul>
                <div class="around-right-more">
                    <div class="around-right-eight" v-for="e in getEight">
                        <div class="eight-left">
                            <div class="around-right-eight-name">
                                {{e.name}}
                            </div>
                            <div class="around-right-eight-price">
                                {{e.price}}
                            </div>
                        </div>
                        <div class="around-eight-img-content">
                            <img :src="e.pic" class="around-right-eight-img">
                        </div>
                    </div>
                    <div class="around-more">
                        <div class="see-more-left">
                             <div class="see-more">浏览更多</div>
                        </div>
                       
                        <div class="see-more-img">
                            <img src="../../assets/img/more.png">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            key:'hot'
        }
    },
    props:['roundData1'],
    computed:{
        getFirstList:function(){
            var list=[];
            var data=this.roundData1.menu;
            for(var i=0;i<data.length;i++){
                if(this.key==data[i].key){
                    var goods=data[i].goods;
                    for(var j=0;j<4;j++){
                        list.push(goods[j]);
                    }
                }
            }
            return list;
        },
        getSecondList:function(){
            var list=[];
            var data=this.roundData1.menu;
            for(var i=0;i<data.length;i++){
                if(this.key==data[i].key){
                    var goods=data[i].goods;
                    for(var j=4;j<7;j++){
                        list.push(goods[j]);
                    }
                }
            }
            return list;
        },
        getEight:function(){
            var list=[];
            var data=this.roundData1.menu;
             for(var i=0;i<data.length;i++){
                if(this.key==data[i].key){
                    var goods=data[i].goods;
                    for(var j=7;j<8;j++){
                        list.push(goods[j]);
                    }
                }
            }
            return list;
        }
    },
    methods:{
        changeItems:function(key){
            this.key=key;
        }
    }
}
</script>
<style>
.around-container{
    width: 100%;
    height: 686px;
}
.around-head{
    height: 58px;
    line-height: 58px;
}
.around-title{
    font-size: 22px;
    float: left;
}
.around-menu{
    float: right;
}
.around-menu-ul{
    margin: 0;
    padding: 0;
    list-style: none;
}
.around-menu-li{
    float: left;
    margin-left: 30px;
    font-size: 16px;
    line-height: 28px;
}
.around-menu-li:hover{
    float: left;
    margin-left: 30px;
    font-size: 16px;
    color:#FF6700;
    border-bottom:2px solid #FF6700;
    line-height: 28px;
}
.around-menu-li-hover{
    float: left;
    margin-left: 30px;
    font-size: 16px;
    color:#FF6700;
    border-bottom:2px solid #FF6700;
    line-height: 28px;
}
.around-content{
    position: absolute;
    top: 58px;
    left: 0;
    width: 100%;
    height: 628px;
}
.around-left{
    position: absolute;
    top: 0;
    left: 0;
    width: 20%;
    height: 628px;
}
.around-left-img1{
    position: absolute;
    top: 0;
    left: 0;
    float: left;
    height: 300px;
    width: 100%;
    margin-bottom: 14px;
}
.around-left-img1:hover{
    position: absolute;
    float: left;
    height: 300px;
    width: 100%;
    top: 0;
    left: 0;
    margin-bottom: 14px;
    margin-top: -2px;
    box-shadow: 5px 5px 5px #ccc;
    transition:all 0.3s;
    cursor: pointer;
}
.around-left-img2{
    position: absolute;
    top: 310px;
    left: 0;
    float: left;
    height: 300px;
    width: 100%;
    margin-bottom: 14px;
}
.around-left-img2:hover{
    position: absolute;
    top: 310px;
    left: 0;
    float: left;
    height: 300px;
    width: 100%;
    margin-bottom: 14px;
    margin-top: -2px;
    box-shadow: 5px 5px 5px #ccc;
    transition:all 0.3s;
    cursor: pointer;
}
.around-right{
    position: absolute;
    width: 80%;
    top: 0;
    left: 20%;
}
.around-right-ul{
    margin: 0;
    padding: 0;
    float: left;
    width: 100%;
    list-style: none;
}
.around-right-li{
    float: left;
     width:24%;
     height:300px;
     margin-left: calc(1% - 2px);
     border: 1px solid #ccc;
     margin-bottom: 7px;
}
.around-right-li:hover{
     float: left;
     width:24%;
     height:300px;
     margin-left: calc(1% - 2px);
     border: 1px solid #ccc;
     margin-top: -2px;
     transition:all 0.3s;
     box-shadow: 5px 5px 10px #ccc;
}
.around-img-content{
    text-align: center;
}
.around-right-img{
    width: 150px;
    height: 150px;
    margin-top: 35px;
}
.around-right-name{
    text-align: center;
    font-size: 14px;
    margin-top: 10px;
}
.around-right-price{
    text-align: center;
    font-size: 14px;
    color: #FF6700;
    margin-top: 5px;
}
.around-right-rank{
    text-align: center;
    color: #ccc;
    margin-top: 10px;
}
.around-right-more{
    position: absolute;
    top:307px;
    right: 0;
    width:24%;
    height:300px;
}
.around-right-eight{
    position: absolute;
    top: 0;
    left: -2px;
    height: 146.5px;
    width: 100%;
    border: 1px solid #ccc;
    margin-bottom: 7px;
}
.around-right-eight:hover{
    position: absolute;
    top: 0;
    left: -2px;
    height: 146.5px;
    width: 100%;
    border: 1px solid #ccc;
    margin-bottom: 7px;
    margin-top: -2px;
    transition:all 0.3s;
    box-shadow: 5px 5px 10px #ccc;
}
.eight-left{
    position: absolute;
    width: 50%;
    text-align: center;
    left: 20px;
}
.around-eight-img-content{
    float: right;
    height:150px;
    line-height: 150px;
}
.around-right-eight-img{
    margin-top: 35px;
    width: 80px;
    height: 80px;
    margin-right: 20px;
}
.around-right-eight-name{
    font-size: 14px;
    width: 94px;
    text-overflow:ellipsis;
    white-space: nowrap;
    overflow: hidden; 
    margin-top: 60px;
    font-size: 14px;
}
.around-right-eight-price{
    color: #FF6700;
    font-size: 14px;
    text-align: left;
    margin-top: 7px;
}
.around-more{
    position: absolute;
    top: 154px;
    left: -2px;
    height: 146.5px;
    width: 100%;
    border: 1px solid #ccc;
}
.around-more:hover{
    position: absolute;
    top: 154px;
    left: -2px;
    height: 146.5px;
    width: 100%;
    border: 1px solid #ccc;
    margin-top: -2px;
    transition:all 0.3s;
    box-shadow: 5px 5px 10px #ccc;
}
.see-more-left{
    position: absolute;
    width: 50%;
    text-align: center;
    left: 20px;
}
.see-more{
    float: left;
    height:150px;
    line-height: 150px;
    font-size: 18px;
}
.see-more-img{
    float: right;
    margin: 50px 30px 0 0; 
}
</style>
