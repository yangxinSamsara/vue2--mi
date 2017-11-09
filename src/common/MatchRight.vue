<template>
    <div class="match-right">
       <ul class="right-goods-content">
           <li class="goods-item" v-for="goods in currGoods" :key="goods.imgUrl">
               <span class="discount-txt" :class="goods.discountType">
                   {{goods.discount}}
               </span>
               <a :href="goods.sourceUrl">
                   <img :src="goods.imgUrl" alt="">
                   <h3>{{goods.title}}</h3>
               </a>
               <p class="goods-price">
                   ￥{{goods.price}}元
                   <span v-if="goods.discountType==='discount'" class="oldPrice">
                      ￥{{goods.oldPrice}}元
                   </span>
               </p>
               <p class="goods-comment">{{goods.heat}}人评价</p>
               <div class="review" v-show="goods.reviewStatus">
                   <span class="review-desc">{{goods.reviewDesc}}</span>
                   <span class="review-auth">来自于{{goods.reviewAuthor}}的评价</span>
               </div>
           </li>
       </ul>
    </div>
</template>
<script>
export default {
  props: ["curr-goods"],
};
</script>

<style lang="scss">
.match-right {
  float: left;
  width: 992px;
  height: 628px;
  .right-goods-content {
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    width: 100%;
    height: 100%;
    .goods-item {
      position: relative;
      margin: 0 0 14px 14px;
      width: 234px;
      height: 260px;
      background: #fff;
      padding: 20px 0;
      cursor: pointer;
      transition: all 0.3s;
      &:hover {
        transform: translateY(-1px);
        box-shadow: 5px 5px 20px #ccc;
        .review {
          height: 76px;
          opacity: 1;
        }
      }
      .discount-txt {
        position: absolute;
        top: 0;
        left: 50%;
        width: 64px;
        height: 20px;
        line-height: 20px;
        margin-left: -32px;
        font-size: 12px;
        text-align: center;
        color: #fff;
        z-index: 4;
        &.free {
          background-color: #ffac13;
        }
        &.new {
          background-color: #83c44e;
        }
        &.discount {
          background-color: #e53935;
        }
      }
      img {
        display: block;
        height: 160px;
        width: 160px;
        margin: 0 auto;
      }
      h3 {
        font-size: 14px;
        text-align: center;
        color: #ccc;
        font-weight: normal;
        text-overflow: ellipsis;
        white-space: nowrap;
        overflow: hidden;
      }
      .goods-price {
        color: #ff6700;
        font-size: 14px;
        text-align: center;
      }
      .oldPrice {
        color: #424242;
        text-decoration: line-through;
      }
      .goods-comment {
        margin: 0 10px;
        font-size: 12px;
        text-align: center;
        color: #b0b0b0;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      .review {
        position: absolute;
        left: 0;
        bottom: 0;
        width: 234px;
        font-size: 12px;
        line-height: 18px;
        overflow: hidden;
        box-sizing: border-box;
        color: #fff;
        background: #ff6700;
        opacity: 0;
        transition: all 0.3s;
        .review-desc {
          display: block;
          text-align: center;
          margin: 8px 30px;
        }
        .review-auth {
          display: block;
          text-align: center;
          margin-bottom: 8px;
        }
      }
    }
  }
}

</style>