<template>
  <div class="find">
    <div class="find-box">
      <div class="find-left" id="findLeft">
        <img src="..\assets\findLeft.png" alt="">
      </div>
      <div class="find-scoll">
        <div class="goods-list" id="list">
          <template v-for="(good,i) in goods">
            <div :key="i" v-if="i%2==0" class="goods1">
              <img :src=good.img alt="">
              <div class="good-name">{{good.name}}</div>
            </div>
            <div :key="i" v-if="i%2==1" class="goods2">
              <div class="good-name">{{good.name}}</div>
              <img :src=good.img alt="">
            </div>
          </template>
        </div>
        <span class="scoll-line" id="line"></span>
        <span class="scoll-point" id="point"></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'find',
  data() {
    return {
      goods:[
        {img:'https://img13.360buyimg.com/ceco/s300x300_jfs/t1/122362/36/8850/47232/5f295bf6E5920468b/fdacbf3366737915.jpg!q70.jpg.webp',
        name:'5G手机'},
        {img:'https://img10.360buyimg.com/ceco/s300x300_jfs/t1/88615/16/9130/197442/5e0b101aE2e4164d0/8767740c293ce85b.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img10.360buyimg.com/ceco/s300x300_jfs/t1/128279/28/5715/89997/5ef7f5a4E21738d65/de12ffebf47a786d.jpg!q70.jpg.webp',
        name:'5G手机'},
        {img:'https://img20.360buyimg.com/ceco/s300x300_jfs/t1/149113/6/4603/71598/5f2a66ceEb2ada927/0afed4942dde8fab.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img30.360buyimg.com/mobilecms/s300x300_jfs/t20512/97/1877004480/48693/f73d42ad/5b3b2831Nd57d1637.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img11.360buyimg.com/ceco/s300x300_jfs/t1/122343/37/2043/87997/5ec247a3E29f68794/56f0a49e2c872a3b.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img13.360buyimg.com/ceco/s300x300_jfs/t1/110183/17/3031/71870/5e0d5c71Ef7fe58ac/732b39413cbf36a0.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img14.360buyimg.com/ceco/s300x300_jfs/t1/113718/1/14261/115672/5f2baf71E17f66b6a/1e3cf8d635098da7.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img14.360buyimg.com/ceco/s300x300_jfs/t1/102488/25/10920/30362/5e205cffEf33febff/50955b5f4c67b127.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img11.360buyimg.com/mobilecms/s300x300_jfs/t1/104272/16/5401/72421/5deda8bfE14185eee/c42117d8c01bdb31.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img13.360buyimg.com/ceco/s300x300_jfs/t1/122362/36/8850/47232/5f295bf6E5920468b/fdacbf3366737915.jpg!q70.jpg.webp',
        name:'5G手机'},
        {img:'https://img10.360buyimg.com/ceco/s300x300_jfs/t1/88615/16/9130/197442/5e0b101aE2e4164d0/8767740c293ce85b.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img10.360buyimg.com/ceco/s300x300_jfs/t1/128279/28/5715/89997/5ef7f5a4E21738d65/de12ffebf47a786d.jpg!q70.jpg.webp',
        name:'5G手机'},
        {img:'https://img20.360buyimg.com/ceco/s300x300_jfs/t1/149113/6/4603/71598/5f2a66ceEb2ada927/0afed4942dde8fab.jpg!q70.jpg.webp',
        name:'运动T恤'},
        {img:'https://img30.360buyimg.com/mobilecms/s300x300_jfs/t20512/97/1877004480/48693/f73d42ad/5b3b2831Nd57d1637.jpg!q70.jpg.webp',
        name:'运动T恤'},
            ]
    }
  },
  mounted: function(){
    // 滚动条实现
    var list = document.getElementById("list");
    var scollPoint = document.getElementById("point");
    scollbar(scollPoint);
    function scollbar(obj) {
        obj.onmousedown = function(ev){
        var oevent=ev||event;
        var distanceX = oevent.clientX - scollPoint.offsetLeft;
        var m=0;
        var n=0;
        // 清除滚动动画
        scollPoint.style.animation='none'
        list.style.animation='none'
        document.onmousemove = function(ev) {
          var oevent=ev||event;
          scollPoint.style.marginLeft='15px'
          if(scollPoint.style.marginLeft.slice(0,-2)>=15&&scollPoint.style.marginLeft.slice(0,-2)<=document.getElementById('line').offsetWidth-64){
            
            // 计算偏移量使图片随滚动条移动
            scollPoint.style.marginLeft = oevent.clientX - distanceX-200-document.getElementById('findLeft').offsetLeft+'px'
            list.style.marginLeft = -(oevent.clientX - distanceX-200-document.getElementById('findLeft').offsetLeft-15)*2000/(document.getElementById('line').offsetWidth-79)+'px'
            
            // 设置边界,要在设置偏移量之前进行判断
            if(scollPoint.style.marginLeft.slice(0,-2)<15){
              list.style.marginLeft = '0px'
              scollPoint.style.marginLeft = '15px'
            }else if (scollPoint.style.marginLeft.slice(0,-2)>document.getElementById('line').offsetWidth-64){
              scollPoint.style.marginLeft = document.getElementById('line').offsetWidth-64+'px'
              list.style.marginLeft = '-2000px'
            }
            
            // 获取偏移量
            m=scollPoint.style.marginLeft.slice(0,-2)-15
            n=list.style.marginLeft.slice(0,-2)
          }
          // 移动时滚动条继续显示,滚动暂停
          list.style.animationPlayState='paused'
          scollPoint.style.opacity='1'
          document.getElementById('line').style.opacity='1'
        }
        document.onmouseup = function(ev){
          var oevent=ev||event;
          document.onmousemove = null;
          document.onmouseup = null;

          // 清除样式改动
          scollPoint.removeAttribute("style")
          list.removeAttribute("style")

          // 取消显示滚动条，开始滚动
          list.style.animationPlayState='running'
          document.getElementById('line').style.opacity='0'

          // 通过设置动画开始时间让动画从鼠标放开的位置开始播放
          list.style.animationDelay=25*n/2000+'s'
          scollPoint.style.animationDelay=-25*m/(document.getElementById('line').offsetWidth-79)+'s'
    　　}
      }
    }
  },
  methods: {
    
  }
}
</script>

<style lang="stylus" scoped>
* {
  padding 0
  margin 0
}
.find {
  height 260px
  width 100%
  margin-bottom 20px
  display flex
  justify-content center
}
.find-box {
  width 1190px
  height 100%
  display flex
  flex-direction row
  justify-content space-between
}
.find-left {
  width 190px
  background-color #fff
  img {
    width 100%
  }
}
.find-left:hover {
  cursor pointer
}
// 滚动条
.find-scoll {
  background-color #fff
  width 990px
  overflow-x scroll
  display flex
  flex-direction column
}
.find-scoll::-webkit-scrollbar
{
  height 0px
}
@keyframes scoll {
  0%{margin-left: 0px}
  99.99%{margin-left: -2000px}
  100%{margin-left: 0px}
}

.goods-list {
  display flex
  flex-direction row
  height 100%
  animation scoll 25s linear infinite
}
.goods1 {
  flex-shrink 0
  margin 20px 50px 0 0
  height 180.8px
  width 150px
}
.goods1>img {
  width 150px
  height 150px
}
.goods1>.good-name {
  margin-top 10px
  color #333
  font-size 14px
}
.goods1:hover>img {
  opacity .8
  cursor pointer
}
.goods1:hover>.good-name {
  color #f10214
  cursor pointer
}
.goods2 {
  flex-shrink 0
  margin 50px 50px 0 0
  height 180.8px
  width 150px
}
.goods2>img {
  width 150px
  height 150px
}
.goods2>.good-name {
  margin-bottom 10px
  color #333
  font-size 14px
}
.goods2:hover>img {
  opacity .8
  cursor pointer
}
.goods2:hover>.good-name {
  color #f10214
  cursor pointer
}
.scoll-point {
  width 79px
  height 9px
  background-color #d8d8d8
  border-radius 4px
  margin-bottom 10px
  margin-top -6px
  margin-left: 15px
  animation scollpoint 25s linear infinite
  opacity 0
}
.scoll-line {
  width 960px
  height 3px
  background-color #f3f3f3
  margin-left 15PX
  opacity 0
}
@keyframes scollpoint {
  0%{margin-left: 15px}
  99.99%{margin-left: 896px}
  100%{margin-left: 15px}
}
@keyframes scollpoint2 {

}
.find-scoll:hover>span,.find-scoll:hover>.goods-list {
  opacity 1 !important
  animation-play-state paused !important
}
//响应页面宽度
@media only screen and (max-width: 1350px) {
  .find-scoll {
    width 790px
  }
  .find-box{
    width 990px
  }
  .scoll-line{
    width 760px
  }
  .scoll-point {
    animation scollpoint2 25s linear infinite
  }
  @keyframes scollpoint2 {
  0%{margin-left: 15px}
  99.99%{margin-left: 696px}
  100%{margin-left: 15px}
}
}
</style>