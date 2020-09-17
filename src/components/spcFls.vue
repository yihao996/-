<template>
  <div class="spcFls">
    <div class="spcFls-box">
      <div class="spcFls-sub"></div>
      <div class="spcFls-sub"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'spcFls',
}
</script>

<style lang="stylus" scoped>
.spcFls {
  height 305px
  width 100%
  margin 20px 0
  display flex
  justify-content center
}
.spcFls-box {
  width 1190px
  height 100%
  display flex
  justify-content space-between
}
.spcFls-sub {
  width 590px
  background-color #fff
  height 100%
}


  //响应页面宽度
  @media only screen and (max-width: 1350px) {
    .spcFls-box {
      width 990px
    }
    .spcFls-sub {
      width 490px
    }
  }
</style>