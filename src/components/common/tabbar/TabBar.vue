<template>
  <div class="tabBar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'TabBar'
}
</script>

<style>
 .tabBar {
     display: flex;
     background-color: #f6f6f6;
     position: fixed;
     bottom: 0;
     left: 0;
     right: 0;
     box-shadow: 0 -1px 2px rgba(100,100,100,.2);
 }
</style>