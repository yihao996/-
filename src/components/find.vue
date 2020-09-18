<template>
  <div class="find">
    <div class="find-box">
      <div class="find-left">
        <img src="..\assets\findLeft.png" alt="">
      </div>
      <div class="find-scoll">
        <div class="goods-list">
          <div class="goods" v-for="(good,i) in 10" :key="i"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'find',
}
</script>

<style lang="stylus" scoped>
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
.find-scoll {
  background-color #fff
  width 990px
  overflow-x scroll
}
.goods-list {
  display flex
  flex-direction row
  height 100%
}
.goods {
  flex-shrink 0
  background-color #333
  height 100%
  width 150px
}

  //响应页面宽度
  @media only screen and (max-width: 1350px) {
    .find-scoll {
      width 790px
    }
    .find-box{
      width 990px
    }
  }
</style>