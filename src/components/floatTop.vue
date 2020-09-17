<template>
  <div class="float-top">
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
  </div>
</template>

<script>
export default {
  name: 'float-top',
}
</script>

<style lang="stylus" scoped>
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
.float {
  position fixed
}
.float-top {
  position fixed
  height 52px
  width calc(100% - 16.8px)
  background-color #ffffff
  border-bottom 2px solid #f10214
  display flex
  align-items center
  flex-direction column
}
.query-form-t {
  height 100%
  display flex
  flex-direction row
  justify-content center
  align-items center
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

</style>