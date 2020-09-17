<template>
  <div id="top-back">
    <div id="top" aria-label="顶部导航">
      <div id="location" class="drop">
        <img class="icon1" src="..\assets\位置.png" alt="">
        <div class="text">广东</div>
        <div id="locChoose" class="choose">
          <div v-for="(item,i) in location" :key="i" class="item">
            <div class="chooseText">{{location[i]}}</div>
          </div>
        </div>
      </div>
      <div class="top-right">
        <div style="display:flex;flex-diraction:row;padding:0 8px">
          <div class="text">你好，请登录</div>
          <div class="text" style="color:#f10215;margin-left:5px">免费注册</div>
        </div>
        <div class="sep">|</div>
        <div class="text" style="padding:0 8px">我的订单</div>
        <div class="sep">|</div>
        <div id="myJD" class="drop">
          <div class="text">我的京东</div>
          <img class="icon2" src="..\assets\下拉.png" alt="">
          <div id="myJDChoose" class="choose">
            <div v-for="(item,i) in myJD" :key="i" class="item">
              <div class="chooseText">{{myJD[i]}}</div>
            </div>
          </div>
        </div>
        <div class="sep">|</div>
        <div class="text" style="padding:0 8px">京东会员</div>
        <div class="sep">|</div>
        <div id="myJD" class="drop">
          <div class="text">企业采购</div>
          <img class="icon2" src="..\assets\下拉.png" alt="">
          <div id="myJDChoose" class="choose">
            <div v-for="(item,i) in myJD" :key="i" class="item">
              <div class="chooseText">{{myJD[i]}}</div>
            </div>
          </div>
        </div>
        <div class="sep">|</div>
        <div id="myJD" class="drop">
          <div class="text">客户服务</div>
          <img class="icon2" src="..\assets\下拉.png" alt="">
          <div id="myJDChoose" class="choose">
            <div v-for="(item,i) in myJD" :key="i" class="item">
              <div class="chooseText">{{myJD[i]}}</div>
            </div>
          </div>
        </div>
        <div class="sep">|</div>
        <div id="myJD" class="drop">
          <div class="text">网站导航</div>
          <img class="icon2" src="..\assets\下拉.png" alt="">
          <div id="myJDChoose" class="choose">
            <div v-for="(item,i) in myJD" :key="i" class="item">
              <div class="chooseText">{{myJD[i]}}</div>
            </div>
          </div>
        </div>
        <div class="sep">|</div>
        <div id="myJD" class="drop">
          <div class="text">手机京东</div>
          <div class="icon2"/>
          <div id="myJDChoose" class="choose">
            <div v-for="(item,i) in myJD" :key="i" class="item">
              <div class="chooseText">{{myJD[i]}}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Top',
  data() {
    return {
      location:['北京','上海','天津','广东','上海',
      '天津','广东','上海','天津','广东',
      '上海','天津','广东','上海','天津',
      '广东','上海','天津','广东','上海',
      '天津','广东'],
      myJD:['待处理订单','消息']
    }
  }
}
</script>

<style lang="stylus" scoped>
div {
  flex-shrink 0
  cursor default
}
.icon1 {
  width 18px
}
.icon2 {
  width 15px
  margin-top 2px
}
#top-back {
  display flex
  justify-content center
  width 100%
  background-color #e3e4e5
  border-bottom 1px solid #cccccc
}
#top {
  width 1190px
  height 30px
  display flex
  justify-content space-between
  align-items center
  
}
#location {
  width 50px
  height 30px
  padding 0 4px
  display flex
  justify-content center
  align-items center
  cursor pointer
}
#locChoose {
  transform translateX(calc(50% - 29px))
  width 300px
}
#location:hover {
  width 48px
}
#myJD {
  width 75px
  height 30px
  padding 0 4px
  display flex
  justify-content center
  align-items center
}
#myJD:hover {
  width 73px
}
#myJDChoose {
  transform translateX(calc(50% - 41.5px))
}
.sep {
  font-size 12px
  color #999
  padding 0 4px
}
.top-right {
  display flex
  flex-direction row
  align-items center
}
.choose {
  cursor auto
  position absolute
  padding 10px
  top 31px
  background-color #ffffff 
  border-bottom 1px solid #ccc
  border-left 1px solid #ccc
  border-right 1px solid #ccc
  display none
  z-index 1000
  flex-wrap wrap
}
.item {
  padding 2px 20px 2px 0px
  height 24px
}
.chooseText {
  font-size 12px
  color #999
  padding 0 8px
  height 100%
  display flex
  align-items center
}
.chooseText:hover {
  cursor pointer
  background-color #f10215
  color #fff
}
.drop:hover {
  background-color #ffffff
  border-top 1px solid #ccc
  border-left 1px solid #ccc
  border-right 1px solid #ccc
  border-bottom 1px solid #fff
}

.drop:hover>.choose {
  display flex
}
.text {
  font-size 12px
  color #999
  cursor pointer
}
.text:hover {
  color #f10215
}

  //响应页面宽度
  @media only screen and (max-width: 1350px) {
    #top {
      width 990px
    }
  }
</style>