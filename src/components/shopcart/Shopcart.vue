<template>
  <div class="shopcart">
    <div class="content">
      <div class="content-left">
        <div class="logo-wrapper">
          <div class="logo">
            <span class="icon-shopping_cart"></span>
          </div>
        </div>
        <div class="price"></div>
        <div class="desc"></div>
      </div>
      <div class="content-right">

      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scope lang="less">
.shopcart{
  position: fixed;
  left:0px;
  bottom: 0px;
  z-index: 50;
  height: 48px;
  width: 100%;
  background: #000;
}
</style>
