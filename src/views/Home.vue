<template>
  <div class="home" id="home">
    <floatTop id="floatTop"/>
    <div class="float-right" id="floatRight">
      <div v-for="(item,i) in floatNav" :key="i" class="right-item" @click="goto(item.id)">{{item.name}}</div>
    </div>
    <top/>
    <query/>
    <allNav/>
    <seckill id="seckill"/>
    <spcFls id="spcFls"/>
    <find/>
    
  </div>
</template>

<script>
// @ is an alias to /src
import top from '@/components/top.vue'
import query from '@/components/query.vue'
import allNav from '@/components/allNav.vue'
import seckill from '@/components/seckill.vue'
import spcFls from '@/components/spcFls.vue'
import find from '@/components/find.vue'
import floatTop from '@/components/floatTop.vue'

export default {
  name: 'Home',
  components: {
    top,query,allNav,seckill,spcFls,find,floatTop
  },
  data() {
    return {
      floatNav:[{name:'京东秒杀',id:'seckill'},
      {name:'特色优选',id:'spcFls'},
      {name:'京东秒杀',id:'seckill'},
      {name:'京东秒杀',id:'seckill'},
      {name:'京东秒杀',id:'seckill'},
      {name:'京东秒杀',id:'seckill'},
      {name:'京东秒杀',id:'seckill'},]
    }
  },
  mounted: function(){
    var mytime = setInterval(go,10)
    function go(){
      var t =document.getElementById("home").scrollTop;
      if( t >=682) {
        document.getElementById("floatTop").style="margin-top:0;transition: 0.4s"
        document.getElementById("floatRight").style="position:fixed;transform:none"
      }else {
        document.getElementById("floatTop").style="margin-top:-54px;transition: 0.4s"
        document.getElementById("floatRight").style="position:absolute;transform:translate(8.4px, 605px)"
      }
    }
  },
  methods: {
    goto(id){
      document.getElementById("home").scrollTop=document.getElementById(id).offsetTop-70
    }
  }
}
</script>

<style lang="stylus" scoped>
.home {
  background-color #f5f5f5
  position fixed
  height 100%
  width 100%
  overflow-y:scroll
}
#floatTop {
  margin-top -54px
}
// 右悬浮栏
.float-right {
  position absolute
  transform translate(8.4px,605px)
  margin-top 77px
  background-color #fff
  width 58px
  height calc(58px * 7)
  margin-left calc(50% + 1190px / 2 + 20px - 16.8px / 2)
  display flex
  flex-direction column
  justify-content center
  align-items center
}
.right-item {
  height 58px
  width 28px
  padding 0 15px
  color #333
  font-size 14px
  display flex
  flex-direction column
  justify-content center
  align-items center
}
.right-item:nth-child(2) {
  color #f10214
}
.right-item:hover {
  background-color #c81623
  color #ffffff
  cursor pointer
}

  //响应页面宽度
  @media only screen and (max-width: 1350px) {
    .float-right {
      margin-left calc(50% + 990px / 2 + 20px - 16.8px / 2)
    }
  }
</style>