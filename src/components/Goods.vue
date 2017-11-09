<template>
  <div class="goods-box">
      <goods-smart></goods-smart>
      <goods-match></goods-match>
      <recommend></recommend>
      <hot-product></hot-product>
      <goods-content></goods-content>
      <my-video></my-video>
  </div>
</template>
<script>
import GoodsSmart from "../common/GoodsSmart";
import GoodsMatch from "../common/GoodsMatch";
import Recommend from "../common/Recommend";
import HotProduct from "../common/HotProduct";
import GoodsContent from "../common/GoodsContent";
import Video from "../common/Video";
export default {
  components: {
    "goods-smart": GoodsSmart,
    "goods-match": GoodsMatch,
    'recommend': Recommend,
    "hot-product": HotProduct,
    "goods-content":GoodsContent,
    "my-video":Video
  }
};
</script>
<style lang="scss" scoped>
.goods-box {
  width: 100%;
  height: auto;
  background: #f5f5f5;
  padding-bottom: 40px;
}
</style>