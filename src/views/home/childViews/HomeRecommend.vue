<template>
  <div class="recommend" :recommend="recommends">
    <div class="recommend-item" v-for="item in recommends.list" :key="item">
      <a :href="item.link">
        <img :src="item.image">
          <div>{{item.title}}</div>
        </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommends: {
      type: Array,
      default() {
        return []
      }
    }
  }
}
</script>

<style>
  .recommend {
      display: flex;
      width: 100%;
      height:30%;
      text-align: center;
      padding: 10px 0 20px;
      border-bottom: 8px solid #eee;
  }
  .recommend-item {
      flex: 1;
      width: 25%;
  }
  .recommend-item img {
      width: 85%;
      padding-bottom: 5px;
  }
</style>