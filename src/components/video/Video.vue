<template>
    <div class="video-container">
        <div class="video-head">
            <div class="video-head-title">视频</div>
            <div class="video-head-menu">查看全部</div>
        </div>
        <div class="video-content">
            <div class="video-content-container" v-for=" video in videos " @click="palyVideo(video)">
                <video  :src="video.src" :poster="video.posterImg" class="video-content-video">
                </video>
                <div class="video-name">{{video.name}}</div>
                <div class="video-info">{{video.info}}</div>
            </div>
        </div>

        <div class="video-mask" v-if="selecVideo"></div>
        <transition name="video">
        <div class="video-float-container" v-if="selecVideo" >
            <div class="video-float-head">
                <div class="video-float-title">
                    {{selecVideo.name}}
                </div>
                <div class="video-float-menu">
                    <span class="video-float-close" @click="closeVideo"></span>
                </div>
            </div>
            <div class="video-float-content">
                <video  controls="controls" :poster="selecVideo.posterImg" preload="auto" class="video-float-video">
                    <source src="movie.ogg" type="video/ogg" />
                    <source :src="selecVideo.src" type="video/mp4" />
                </video>
            </div>
        </div>
        </transition>
    </div>
</template>
<script>
import '../../assets/fonts/style.css';

export default {
    data(){
        return{
            videos:[{
                name:'小米8，一部与众不同的手机',
                src:'https://v.mifile.cn/b2c-mimall-media/ed921294fb62caf889d40502f5b38147.mp4',
                posterImg:'http://i1.mifile.cn/a4/xmad_15278351912522_frJQc.jpg',
                info:'透明探索版，将科技与美学完美结合'
            },{
                name:'小米MIX 2S，一面科技 一面艺术',
                src:'https://v.mifile.cn/b2c-mimall-media/53fc775dd6b29ecd8df3e2ea35129766.mp4',
                posterImg:'http://i1.mifile.cn/a4/xmad_15278359339164_dDTJC.jpg',
                info:'艺术品般陶瓷机身，惊艳、璀璨'
            },{
                name:'天生丽质的小米6X',
                src:'https://v.mifile.cn/b2c-mimall-media/4c2ab855040d19a0680cb2064097a313.mp4',
                posterImg:'http://i1.mifile.cn/a4/xmad_15278359181775_apkZK.jpg',
                info:'让你一见倾心'
            },{
                name:'生活中无所不在的小爱同学',
                src:'https://v.mifile.cn/b2c-mimall-media/69f7b9881f4ed7123f0d473dcd44d621.mp4',
                posterImg:'http://i1.mifile.cn/a4/xmad_15278358912266_LDHfI.jpg',
                info:'一句话搞定手机复杂操作'
            }],
            selecVideo:''
        }
    },
    methods:{
        palyVideo:function(data){
            this.selecVideo=data;
        },
        closeVideo:function(){
            this.selecVideo='';
        }
    }
}
</script>
<style>
.video-container{
    position: absolute;
    top:3961px;
    width: 90%;
    height: 348px;
    left: 5%;
    margin-top: 26px;
}
.video-head{
    position: absolute;
    top: 0;
    left: 0;
    height: 58px;
    width: 100%;
}
.video-head-title{
    height: 58px;
    width: auto;
    float: left;
    line-height: 58px;
    font-size: 22px;
}
.video-head-menu{
    float: right;
    cursor: pointer;
    height: 58px;
    line-height: 58px;
    font-size: 16px;
}
.video-head-menu:hover{
    float: right;
    cursor: pointer;
    height: 58px;
    line-height: 58px;
    font-size: 16px;
    color: #FF6700;
}
.video-content{
    position: absolute;
    top:58px;
    left: 0;
    height:290px ;
    width: 100%;
}
.video-content-container{
    width:24%;
    height: 280px;
    float: left;
    margin: 5px calc(1% - 2px) 5px 0;
    border: 1px solid #ccc;
}
.video-content-container:hover{
    width:24%;
    height: 280px;
    float: left;
    margin: 5px calc(1% - 2px) 5px 0;
    border: 1px solid #ccc;
    margin-top: -2px;
    transition: all 0.3s;
    box-shadow: 5px 5px 5px #ccc;
}
.video-content-video{
    width: 100%;
    height: 180px;
    margin-top: -2px;
    cursor: pointer;
}
.video-name{
    text-align: center;
    font-size: 14px;
    margin-top: 20px;
}
.video-name:hover{
    text-align: center;
    font-size: 14px;
    margin-top: 20px;
    color: #FF6700;
    cursor: pointer;
}
.video-info{
    text-align: center;
    font-size: 14px;
    margin-top: 10px;
    color: #ccc;
}
.video-mask{
    position: fixed;
    width: 100%;
    height: 100%;
    background: #fff;
    opacity:0.3;
    z-index: 100;
    top:0;
    left: 0;
}
.video-float-container{
    position: fixed;
    width: 880px;
    height: 586px;
    background: #fff;
    z-index: 100;
    top:calc(50% - 293px);
    left:calc( 50% - 440px);
}
.video-float-head{
    position: absolute;
    height: 50px;
    width: 100%;
    z-index: 200;
    opacity:1;
    top:0;
    left:0;
    background: #ccc;
    opacity:1;
}
.video-float-content{
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: 200;
    opacity:1;
    top:50px;
}
.video-float-title{
    float: left;
    line-height: 50px;
    margin-left: 20px;
    font-size: 18px;
}
.video-float-menu{
    float: right;
    line-height: 50px;
}
.video-float-close:before{
    width: 30px;
    height: 30px;
    margin: 10px 20px 0 0;
    font-family: 'icomoon' !important;
    color: #000;
    font-size: 30px;
    cursor: pointer;
}
.video-float-close::after{
    width: 30px;
    height: 30px;
    margin: 10px 20px 0 0;
    font-family: 'icomoon' !important;
    color:#FF6700;
    cursor: pointer;
    font-size: 30px;
}
.video-float-video{
    position: absolute;
    width: 880px;
    height:auto;
}

/*.video-enter-active, .video-leave-active {
  transition: opacity .5s;
}
.video-enter, .video-leave-to {
  opacity: 0;
}*/
.video-enter-active {
  animation: bounce-in 1s;
}
.video-leave-active {
  animation: bounce-in 1s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
