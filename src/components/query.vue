<template>
  <div class="query-back">
    <div class="query">
      <img id="JD1" class="JD" src="..\assets\JD1.png" alt="">
      <div class="query-form">
        <div>
          <div class="query-form-t">
            <div class="query-input-box">
              <input class="query-input" type="text">
              <img class="query-icon" src="..\assets\相机.png" alt="">
              <button class="query-btn">
                <img class="query-img" src="..\assets\查找.png" alt="">
              </button>
            </div>
            <div class="my-cart">
              <img class="query-icon" src="..\assets\购物车.png" alt="" style="height:16px;margin-right:5px">
              <div id="my-cart-num">0</div>
              <div class="text" style="color:#f10215">我的购物车</div>
            </div>
          </div>
          <div class="query-form-m">
            <div id="hotText" class="text" v-for="(item,i) in hot" :key="i" style="margin-right:10px">{{item}}</div>
          </div>
        </div>
        <div class="query-form-b">
          <div id="hotNavText" class="text" v-for="(item,i) in hotNav" :key="i" style="margin-right:10px">{{item}}</div>
        </div>
      </div>
      <img id="JD2" class="JD" src="..\assets\JD2.png" alt="">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Query',
  data() {
    return {
      hot:['企业中秋节','热卖家具','家装节','健康5折','图书矩惠','大牌美妆','学生特权'],
      hotNav:['秒杀','优惠券','PLUS会员','品牌闪购','拍卖','京东家电','京东超市','京东生鲜','京东国际','京东金融']
    }
  }
}
</script>

<style lang="stylus" scoped>

#my-cart-num {
  position absolute
  background-color #f10215
  color #ffffff
  font-size 12px
  width 18px
  height 14px
  border-radius 7px
  transform translate(-18px,-50%)
}
*{
    padding 0
    margin 0
    border none
    outline none
    flex-shrink 0
}
.text {
  font-size 12px
  color  #999
  cursor pointer
}
.text:hover {
  color #f10215
}
.query-back {
  display flex
  justify-content center
  width 100%
  background-color #ffffff
  border-bottom 1px solid #cccccc
}
.query {
  height 140px
  width 1190px
  display flex
  justify-content space-between
  align-items center
}
.JD {
  height 120px
  width 190px
  overflow hidden
}
.query-form {
  display flex
  align-items center
  flex-direction column
}
.query-form-t {
  height 60px
  display flex
  flex-direction row
  align-items flex-end
}
.query-input-box {
    height 32px
    width 486px
    border 2px solid #f10215
    display flex
    flex-direction row
    justify-content space-between
    align-items center
}
.query-input {
    height 26px
    width 372px
    padding 2px 0 2px 17px
    margin-left 1px
    color #333
}
.query-icon {
  height 20px
  padding 6px 10px
}
.query-btn {
    width 58px
    height 32px
    display flex
    justify-content center
    align-items center
    background-color #f10215
    cursor pointer
}
.query-btn:hover {
    background-color #d81e06
}
.query-img {
    height 20px
}
.my-cart {
  width 130px
  height 34px
  border 1px solid #e3e4e5
  margin-left 20px
  display flex
  flex-direction row
  justify-content center
  align-items center
}
.my-cart:hover {
  border 1px solid #d81e06
}
.query-form-m {
  display flex
  flex-direction row
  height 20px
}
#hotText:first-child {
  color #f10215
}
#hotText:first-child:hover {
  color #d81e06
}
.query-form-b {
  height 40px
  padding-top 20px
  display flex
  align-items center
}
#hotNavText {
  font-size 15px
  color #333
  margin 0 11px
}
#hotNavText:hover {
  color #f10215
}
#hotNavText:first-child {
  color #f10215
  font-weight bolder
}
#hotNavText:nth-child(2) {
  font-weight bolder
  color #f10215
}
#hotNavText:first-child:hover {
  color #d81e06
}
#hotNavText:nth-child(2):hover {
  color #d81e06
}
</style>