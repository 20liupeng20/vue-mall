<template>
  <div>
      <nav-bar class="home-nav-bar"><div slot="center">购物街</div></nav-bar>
      <home-swiper :banners="banners"></home-swiper>
      <home-recommend :recommends="recommends"></home-recommend>
  </div>
</template>

<script>

import NavBar from 'components/common/navbar/NavBar'
import HomeSwiper from './childViews/HomeSwiper'
import HomeRecommend from './childViews/HomeRecommend'
import {getHomeMultiData} from 'network/home'
export default {
  name: 'Home',
  data() {
    return {
      banners: [],
      recommends: []
    }
  },
  created() {
    getHomeMultiData().then(res => {
      this.banners = res.data.banner
      this.recommends = res.data.recommend
    }).catch(err => {

    })
  },
  components: {
    NavBar,
    HomeSwiper,
    HomeRecommend
  }
}
</script>

<style>
  .home-nav-bar {
    position: flex;
    background: var(--color-tint);
    left: 0;
    right: 0;
    top: 0;
    z-index:10
  }
</style>