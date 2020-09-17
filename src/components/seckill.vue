<template>
  <div class="seckill">
    <div class="seckill-box">
      
    </div>
  </div>
</template>

<script>
  export default {
    name: 'seckill',
  }
</script>

<style lang="stylus" scoped>
.seckill {
  height 260px
  width 100%
  margin-bottom 20px
  display flex
  justify-content center
}
.seckill-box {
  width 1190px
  height 100%
  background-color #fff
}

  //响应页面宽度
  @media only screen and (max-width: 1350px) {
    .seckill-box {
      width 990px
    }
  }
</style>