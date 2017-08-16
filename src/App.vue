<template>
  <div id="app">
    <headers :seller="seller"></headers>
    <div class="tab">
      <div class="tab-item border-1px">
        <router-link to="/goods">商品</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/ratings">评论</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/seller">商家</router-link>
      </div>
    </div>
    <router-view :seller="seller"></router-view>
  </div>
</template>

<script>
import Headers from './components/header/Header'
export default {
  name: 'app',
  components: {
    Headers
  },
  data() {
    return {
      seller: {}
    }
  },
  created() {
    let axios = this.$axios
    axios.get('http://118.184.85.83:8082/seller')
      .then((res) => {
        if (res.status === 200) {
          this.seller = res.data[0].seller
        }
      })
  }
}
</script>

<style scope lang="less">
@import './common/less/index';
#app {
  .tab {
    display: flex;
    width: 100%;
    height: 40px;
    line-height: 40px; // border-bottom: 1px solid rgba(7, 17, 27, 0.1);
    .border-1px(rgba(7, 17, 27, 0.1));
    .tab-item {
      flex: 1;
      text-align: center;
      &>a {
        display: block;
        font-size: 14px;
        color: rgb(77, 85, 93);
        &.active {
          color: rgb(240, 20, 20);
        }
      }
    }
  }
}
</style>
