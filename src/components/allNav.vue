<template>
  <div id="allNav">
    <div id="drop-img"><img src="..\assets\dropImg1.png" style="height:100%" alt=""></div>
    <div id="drop-img-all"><img src="..\assets\dropImg2.png" style="height:100%;width:790px" alt=""></div>
    <div id="nav">
      <div id="nav1">
        <div v-for="(item,i) in navItems1" :key="i" class="nav1-item">
          <div class="navText">{{item}}</div>
          <div class="nav-watch">
            <div class="nav-watch-left">
              <div class="nav-watch-top">
                <div v-for="(topItem,topi) in navItems2" :key="topi" class="nav-watch-top-item">{{topItem}} 
                  <img src="..\assets\右箭头白.png" alt=""> 
                </div>
              </div>
              <div class="nav-watch-bottom">
                <div v-for="(bottomItem,boti) in navItems3" :key="boti" class="nav-watch-item">
                  <div class="nav-watch-title">{{bottomItem.title}}<img src="..\assets\右箭头黑.png" alt=""></div>
                  <div class="nav-watch-centent">
                    <div v-for="(item,index) in bottomItem.items" :key="index" class="nav-watch-sub">{{item}}</div>
                  </div>
                </div>
              </div>
            </div>
            <div class="nav-watch-right"></div>
          </div>
        </div>
      </div>
      <div id="nav2">
        <div v-for="(img,i) in navImg2" :key="i" class="chelab" :id="'chelab'+i"></div>
        <div class="img-scoll">
          <img v-for="(img,i) in navImg2" :key="i" class="nav2-img" :src=img alt="" :id="'img'+i">
        </div>
      </div>
      <div id="nav3">
      </div>
      <div id="nav4">
      </div>
    </div>
    <div id="drop-img" />
  </div>
</template>
<script>
export default {
  name: 'allNav',
  data() {
    return {
      navItems1:['家用电器','手机','电脑','家居','电脑','家居','家用电器','手机','电脑','家居','电脑','家居','家用电器','手机','电脑','家居','电脑','家居'],
      navItems2:['家电馆','家电专卖店','家电专卖店','家电专卖店','家电专卖店'],
      navItems3:[{
        title:'电视',
        items:['超薄电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视','全面屏电视']
      },{
        title:'电视',
        items:['超薄电视','全面屏电视']
      },{
        title:'电视',
        items:['超薄电视','全面屏电视']
      },{
        title:'电视',
        items:['超薄电视','全面屏电视']
      },{
        title:'电视',
        items:['超薄电视','全面屏电视']
      },{
        title:'电视',
        items:['超薄电视','全面屏电视']
      },{
        title:'电视',
        items:['超薄电视','全面屏电视']
      }],
      navImg2:[
          'https://img11.360buyimg.com/babel/s1180x940_jfs/t1/145525/19/7684/100699/5f55a687E973c1f1a/dbc8e965fb532843.jpg.webp',
          'https://img30.360buyimg.com/da/s1180x940_jfs/t1/134870/12/9498/102197/5f5883dbE69126e31/c2bfc109b5923d04.jpg.webp',
          'https://img14.360buyimg.com/pop/s1180x940_jfs/t1/114124/37/17603/57147/5f59ef59E1d7553e7/29d08eb8dfb1af65.jpg.webp',
          'https://imgcps.jd.com/ling4/100006487373/5Lqs6YCJ5aW96LSn/5L2g5YC85b6X5oul5pyJ/p-5bd8253082acdd181d02f9df/78295ca3/cr/s/q.jpg',
          'https://img12.360buyimg.com/pop/s1180x940_jfs/t1/141119/1/8310/99116/5f5c4364E544fa82d/53a585ce2c39790f.jpg.webp',
          'https://img20.360buyimg.com/pop/s1180x940_jfs/t1/111059/11/17519/54245/5f5acbc0E0c59ed1c/b2d3543cfeab3d5a.jpg.webp',
          'https://img20.360buyimg.com/pop/s1180x940_jfs/t1/134699/19/9574/83901/5f5b1174Ec6451061/be971439f60acd72.jpg.webp',
          'https://img13.360buyimg.com/pop/s1180x940_jfs/t1/149451/36/8007/82560/5f5ad102Ead0dd66b/c608c1df75a2efaf.png.webp'
        ]
    }
  },
  methods:{

  }
}
</script>
<style lang="stylus" scoped>
  #allNav {
    height 480px
    width 100%
    margin-bottom 30px
    display flex
    flex-direction row
    justify-content center
  }
  // 左部图片广告
  #drop-img {
    cursor pointer
    width calc(50% - 595px)
    height 470px
    display flex
    align-items flex-end
    flex-direction column
    padding-top 10px
  }
  #drop-img:hover+div{
    width 790px
  }
  #drop-img-all {
    cursor pointer
    z-index 1000
    width 0
    height 470px
    padding-top 10px
    position absolute
    left 50%
    transform translateX(-595px)
    transition: 0.5s
    -webkit-transition: 0.5s
    overflow hidden
  }
  #drop-img-all:hover{
    width 790px
  }
  //导航框整体结构
  #nav {
    width 1190px
    display flex
    flex-direction row
    padding 0
  }
  #nav1 {
    width 190px
    height 450px
    background-color #fff
    margin-right 10px
    margin-top 10px
    padding 10px 0
  }
  #nav2 {
    width 590px
    height 470px
    background-color red
    margin-right 10px
    margin-top 10px
    overflow hidden
  }
  #nav3 {
    width 190px
    height 470px
    background-color #fff
    margin-right 10px
    margin-top 10px
  }
  #nav4 {
    width 190px
    height 470px
    background-color #fff
    margin-top 10px
  }
  // 导航栏一
  .nav1-item {
    height 25px
    width 172px
    padding 0 0 0 18px
    color #636363
    font-size 14px
    display flex
    justify-content flex-start
    align-items center
  }
  .nav1-item:hover {
    background-color #d9d9d9
  }
  .navText:hover {
    color #d81e06
    cursor pointer
  }
  .nav1-item:hover>.nav-watch{
    display flex
  }
  .nav-watch {
    position absolute
    width 1000px
    height 440px
    top 182px
    transform translateX(calc(50% - 330px))
    background-color #ffffff
    box-shadow 2px 0 5px #aaa
    display none
    padding 20px 0 10px 0
  }
  .nav-watch-left {
    width 600px
    display flex
    flex-direction column
  }
  .nav-watch-top {
    width 580px
    padding 0 0 0 20px
    height 24px
    width auto
    display flex
    flex-direction row
  }
  .nav-watch-top-item {
    height 24px
    display flex
    justify-content center
    align-items center
    font-size 12px
    padding 0 10px
    margin-right 10px
    color #fff
    background-color #333
    cursor pointer
  }
  .nav-watch-top-item:hover {
    background-color #c81623
  }
  .nav-watch-top-item>img {
    width 12px
    margin-left 5px
  }
  .nav-watch-bottom {
    width 580px
    padding 10px 0 0 20px
  }
  .nav-watch-item {
    display flex
    flex-direction row
    align-items flex-start,'全面屏电视','全面屏电视'
  }
  .nav-watch-title {
    font-size 12px
    width 70px 
    display flex
    margin-top 8px
    height 16px
    justify-content flex-end
    align-items center
    font-weight bold
    color #333
  }
  .nav-watch-title:hover {
    color #c81623
    cursor pointer
  }
  .nav-watch-title>img {
    width 12px
    margin-left 5px
    height 12px
  }
  .nav-watch-centent {
    display flex
    flex-direction row
    flex-wrap wrap
    margin-left 10px
    padding 5px 0
    width 500px
  }
  .nav-watch-sub {
    padding 0 7px
    margin 3px 0
    font-size 12px
  }
  .nav-watch-sub:hover {
    color #c81623
    cursor pointer
  }
  // 导航栏二（轮播图）
  .nav2-img {
    width 590px
    padding 0
  }
  .img-scoll {
    display flex
    flex-direction column
    animation lbt 24s linear infinite
  }
  .img-scoll:hover {
    animation-play-state paused
    cursor pointer
  }
  @keyframes lbt {
    0%{margin-top:0}
    12.49%{margin-top:0}

    12.5%{margin-top:-470px}
    24.99%{margin-top:-470px}

    25%{margin-top:-940px}
    37.49%{margin-top:-940px}

    37.5%{margin-top:-1410px}
    49.99%{margin-top:-1410px}

    50%{margin-top:-1880px}
    62.49%{margin-top:-1880px}

    62.5%{margin-top:-2350px}
    74.99%{margin-top:-2350px}

    75%{margin-top:-2820px}
    87.49%{margin-top:-2820px}

    87.5%{margin-top:-3290px}
    99.99%{margin-top:-3290px}
    100%{margin-top:0}
  }
  .chelab {
    position absolute
    z-index 999
    display block
    margin-right 5px
    width 10px
    height 10px
    background-color rgba(255,255,255,0.4)
    border-radius 50%
  }
  .chelab:hover {
    background-color #fff
    width 9px
    height 9px
    box-shadow 0 0 0 3px rgba(255,255,255,0.4)
  }
  #chelab0{
    transform translate(10px,450px)
  }
  #chelab1{
    transform translate(25px,450px)
  }
  #chelab2{
    transform translate(40px,450px)
  }
  #chelab3{
    transform translate(55px,450px)
  }
  #chelab4{
    transform translate(70px,450px)
  }
  #chelab5{
    transform translate(85px,450px)
  }
  #chelab6{
    transform translate(100px,450px)
  }
  #chelab7{
    transform translate(115px,450px)
  }
  .chelab:hover~.img-scoll {
    animation:none
  } 
  #chelab0:hover~.img-scoll {
    margin-top:0
  }
  #chelab1:hover~.img-scoll {
    margin-top:-470px
  }
  #chelab2:hover~.img-scoll {
    margin-top:-940px
  }
  #chelab3:hover~.img-scoll {
    margin-top:-1410px
  }
  #chelab4:hover~.img-scoll {
    margin-top:-1880px
  }
  #chelab5:hover~.img-scoll {
    margin-top:-2350px
  }
  #chelab6:hover~.img-scoll {
    margin-top:-2820px
  }
  #chelab7:hover~.img-scoll {
    margin-top:-3290px
  }

  //响应页面宽度
  @media only screen and (max-width: 1350px) {
    #nav {
      width 990px
    }
    #nav3 {
      display none
    }
    #drop-img{
      display none
    }
  }
</style>