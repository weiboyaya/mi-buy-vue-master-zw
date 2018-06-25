<template>
    <div class="span4">
        <ul v-for="lists in getSpanList" class="span4-ul">
            <li v-for="list in lists" class="span4-li">
                <div class="span4-name">{{list.name}}</div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data(){
        return{
            spanList:[{
                name:'选购手机',
                path:''
            },{
                name:'企业团购',
                path:''
            },{
                name:'F码通道',
                path:''
            },{
                name:'米粉卡',
                path:''
            },{
                name:'以旧换新',
                path:''
            },{
                name:'话费充值',
                path:''
            }]
        }
    },
    computed:{
        getSpanList:function(){
            var lists=[],
                list=[];
            for(var i=1;i<=this.spanList.length;i++){
                if(i%3==0){
                    list.push(this.spanList[i-1]);
                    lists.push(list);
                    list=[];
                }else{
                    list.push(this.spanList[i-1]);
                }
            }
            list.length>0&&lists.push(list);
            return lists;
        }
    }
}
</script>
<style>
.span4{
    position: absolute;
    width: 20%;
}
.span4-ul{
    margin: 0;
    padding: 0;
    width: 100%;
    list-style: none;
    float: left;
}
.span4-li{
    float: left;
    width: 33%;
    height: 85px;
    background: rgba(0, 0, 0, 0.3);
}
.span4-name{
    font-size: 14px;
    color:#ccc;
    width: auto;
    height: 85px;
    line-height: 85px;
    text-align: center;
    border: 0.1px solid #ccc;
    border-left: none;
    border-top: none;
    cursor: pointer;
}
.span4-name:hover{
    font-size: 14px;
    color:white;
    width: auto;
    height: 85px;
    line-height: 85px;
    text-align: center;
    border: 0.1px solid #ccc;
    border-left: none;
    border-top: none;
    cursor: pointer;
}
</style>