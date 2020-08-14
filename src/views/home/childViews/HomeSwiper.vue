<template>
  <swiper :banners="banners">
    <swiper-item v-for="(item,index) in banners.list" :key="index">
      <a :href="item.link">
        <img :src="item.image" :alt="item.title">
      </a>
    </swiper-item>
  </swiper>
</template>

<script>

import {Swiper,SwiperItem} from 'components/common/swiper/index'
export default {
  name: 'HomeSwiper',
  props: {
    banners: {
      type: Array,
      default() {
        return []
      }
    }
  },
  components: {
      Swiper,
      SwiperItem
  }
}
</script>

<style>

</style>