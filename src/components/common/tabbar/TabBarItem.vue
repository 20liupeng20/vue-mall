<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :style="activeStyle"><slot name="item-name"></slot></div>
  </div>
</template>

<script>
export default {
  name: 'TabBarItem',
  props: {
    link: String,
    activeColor: {
      type: String,
      default: 'red'
    }
  },
  data() {
    return {
    }
  },
  computed: {
    isActive() {
      return this.$route.path.includes(this.link)
    },
    activeStyle() {
      return this.isActive ? {color: this.activeColor} : {}
    }
  },
  methods: {
    itemClick() {
      this.$router.replace(this.link).catch(err => {err})
    }
  }
}
</script>

<style>
 .tab-bar-item {
   flex: 1;
   height: 60px;
   text-align: center;
   padding-top: 5px;
 }
 .tabBar .tab-bar-item img {
   width: 30px;
   height: 30px;
   vertical-align: middle;
 }
</style>