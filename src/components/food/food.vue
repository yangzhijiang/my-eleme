<template>
  <div class="food" v-show="showFlag">
  
  </div>
</template>

<script>
export default {
  props: {
    food: {
      type: Object
    }
  }
}
</script>

<style scope lang="less">
.food {
  position: fixed;
  left: 0px;
  top: 0px;
  bottom: 48px;
  z-index: 30;
  width: 100%;
  background: #fff;
}
</style>
