<template>
  <div class="find">
    <div class="find-box">

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
  background-color #fff
}

  //响应页面宽度
  @media only screen and (max-width: 1350px) {
    .find-box {
      width 990px
    }
  }
</style>