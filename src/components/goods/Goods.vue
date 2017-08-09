<template>
  <div class="goods">
    <div class="muen-wrapper">
      <ul>
        <li v-for="item in goods" class="muen-item">
          <span class="text">
            <span v-show="item.type > 0" class="icon" :class="classMap[item.type]"></span>{{ item.name }}
          </span>
        </li>
      </ul>
    </div>
    <div class="foods-wrapper"></div>
  </div>
</template>

<script>
  export default {
    props: {
      seller: {
        type: Object
      }
    },
    data () {
      return {
        goods: []
      }
    },
    created () {
      this.classMap = ['decrease', 'discount', 'guarantee', 'invoice', 'special']
      this.$axios.get('http://118.184.85.83:8082/goods')
      .then((res) => {
        if (res.status === 200) {
          this.goods = res.data[0].goods
          console.log(this.goods)
        }
      })
    }
  }
</script>

<style lang="less">
.goods{
  display: flex;
  position: absolute;
  top: 174px;
  bottom: 46px;
  width: 100%;
  overflow: hidden;
  .muen-wrapper{
    flex: 0 0 80px;
    width: 80px;
    background: #f3f5f7;
    .muen-item{
      display: table;
      height: 54px;
      width: 56px;
      line-height: 14px;
      font-size: 14px;
      .icon {
          display: inline-block;
          vertical-align: top;
          width: 12px;
          height: 12px;
          margin-right: 4px;
          background-size: 12px 12px;
          background-repeat: no-repeat;
          &.decrease {
          }
          &.discount {
          }
          &.guarantee {
          }
          &.invoice {
          }
          &.special {
          }
        }
    }
  }
  .foods-wrapper{
    flex: 1;

  }
}
.bg-image (@url) {
  background-image: url("@{url}@2x.png");
  @media (-webkit-min-device-pixel-ratio: 3), (min-device-pixel-ratio: 3) {
    background-image: url("@{url}@3x.png");
  }
}
</style>
