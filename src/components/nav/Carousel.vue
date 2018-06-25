<template>
    <div class="carousel" @mouseover="stopChange" @mouseout="startChange">
        <img class="carousel-img" :src="path">
        <div class="carousel-index">
            <ul class="carousel-index-ul">
                <li v-for="pic in pictures" :class="path==pic.path?'hover':'carousel-index-li'" @click="selecPic(pic)"></li>
            </ul>
        </div>
        <div class="carousel-previous">
            <img src="../../assets/img/chevron-left.png" class="chevron" @click="previous" />
        </div>
        <div class="carousel-next">
            <img src="../../assets/img/chevron-right.png" class="chevron" @click="next"/>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            pictures:[{
                id:1,
                path:'http://i1.mifile.cn/a4/xmad_152940243093_EgRIT.jpg'
            },{
                id:2,
                path:'http://i1.mifile.cn/a4/xmad_1529377715473_xVjDr.jpg'
            },{
                id:3,
                path:'http://i1.mifile.cn/a4/xmad_15248221330196_tvCXl.jpg'
            },{
                id:4,
                path:'http://i1.mifile.cn/a4/xmad_15293127351522_gPtTj.jpg'
            },{
                id:5,
                path:'http://i1.mifile.cn/a4/xmad_15294894169338_bwDyv.jpg'
            }],
            index:0,
            change:null,
            path:'http://i1.mifile.cn/a4/xmad_152940243093_EgRIT.jpg',
            isSelec:false
        }
    },
    watch:{
        "path":function(){
            var that=this;
            that.change!=null&&clearInterval(that.change);
            if(!this.isSelec){
                that.change= setInterval(function(){
                    that.index==that.pictures.length&&(that.index=0);
                    that.path=that.pictures[(that.index++)%that.pictures.length].path;
                },5000);
            }
            
        }
    },
    computed:{
    },
    methods:{
        stopChange:function(){
           this.change!=null&&clearInterval(this.change);
           this.isSelec=false; 
        },
        startChange:function(){
            var that=this;
            this.isSelec=false;
            that.change= setInterval(function(){
                that.index==that.pictures.length&&(that.index=0);
                that.path=that.pictures[(that.index++)%that.pictures.length].path;
            },5000);
        },
        selecPic:function(data){
            this.change!=null&&clearInterval(this.change);
            this.index=data.id-1;
            var path=this.pictures[this.index%this.pictures.length].path;
            this.isSelec=true;
            this.path=path;
        },
        previous:function(){
            this.change!=null&&clearInterval(this.change);
            this.index=this.index+this.pictures.length-1;
            var path=this.pictures[this.index%this.pictures.length].path;
            this.isSelec=true;
            this.path=path;
        },
        next:function(){
            this.change!=null&&clearInterval(this.change);
            var path=this.pictures[(++this.index)%this.pictures.length].path;
            this.isSelec=true;
            this.path=path;
        }
    },
    mounted:function(){
         this.startChange(); 
    }
}
</script>
<style>
.carousel{
    position: absolute;
    top: 0;
    left: 0;
    height: 460px;
    margin-left: 20%;
    overflow: hidden;
}
.carousel-img{
    width:100%;
    height: 460px;
    
}
.carousel-index{
    position: absolute;
    top:420px;
    left: 40%;
}
.carousel-index-ul{
    list-style: none;
}
.carousel-index-li{
    float: left;
    border:2px solid rgba(0,0,0,0.4);
    border-radius: 50%;
    width: 6px;
    height: 6px;
    margin-left: 7px;
    background: rgba(0,0,0,0.4);
}
.carousel-index-li:hover{
    float: left;
    border:2px solid rgba(0,0,0,0.4);
    border-radius: 50%;
    width: 6px;
    height: 6px;
    margin-left: 7px;
    background:#fff;
    
}
.hover{
    float: left;
    border:2px solid rgba(0,0,0,0.4);
    border-radius: 50%;
    width: 6px;
    height: 6px;
    margin-left: 7px;
    background:#fff;
}
.carousel-previous{
    position: absolute;
    top: 180px;
    left: 0;
}
.carousel-next{
    position: absolute;
    top: 180px;
    right: 0;
}
.chevron{
    width:100px;
    height:100px;
}
.chevron:hover{
    width:100px;
    height:100px;
    background:#ccc;
    cursor: pointer;
}

</style>


