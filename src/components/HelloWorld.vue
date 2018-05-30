<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="wrap">
      <swiper :options="swiperOption" v-if='list.length>0'>
        <swiper-slide v-for = '(i,j) in list' :key='j'>
          <img style="width: 100%;height: 200px" :src="i.src" alt=""/>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: 'HelloWorld',
  components: {
    swiper,
    swiperSlide
  },
  computed:{
    swiperOption () {
      return {
        loop : true,
        autoplay:{
          delay: 4000,
          disableOnInteraction: false,
        },
        pagination: {
          el: '.swiper-pagination',
          bulletClass : 'custom-bullet',
          bulletActiveClass : 'custom-bulletActive',
        }
      }
    }
  },
  data () {
    return {
      msg: 'Welcome to Swiper',
      list:[
        { src:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1527682044519&di=64082fb795bb2d45acdfe9ce5a11e2d2&imgtype=0&src=http%3A%2F%2Fi1.hdslb.com%2Fbfs%2Farchive%2F763293ce06bf1e684ef0ea3da43ae5008d8564b8.jpg'},
        { src:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1527682063424&di=c1b10185eda5d0071eca5d99d44f8374&imgtype=0&src=http%3A%2F%2Fimg5.dwstatic.com%2Flol%2F1512%2F315316081023%2F1451364343108.jpg'},
        { src:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=4177167960,4159008495&fm=27&gp=0.jpg'},
        { src:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1527682201637&di=8e569277556f26b8bd0ed8083d332ec1&imgtype=0&src=http%3A%2F%2Fpic1.win4000.com%2Fwallpaper%2F6%2F59ba1ea434c1c.jpg'},
      ],
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
