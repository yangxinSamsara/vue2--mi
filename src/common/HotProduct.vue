<template>
  <div class="hotProduct">
      <goods-header :title="title"></goods-header>
      <div class="hot-wrap">
          <ul class="hot-content ">
              <li class="hot-item" v-for="item in hots" :key="item.name">
                  <a :href="item.sourceUrl">
                      <img :src="item.imageUrl" alt="">
                        <p class="review-txt">{{item.review}}</p>
                        <p class="review-author">来自{{item.author}}的评价</p>
                        <div class="item-desc">
                            <span class="item-name">{{item.name}}</span>
                            <span class="sep">|</span>
                            <span class="item-price">￥{{item.price}}元</span>
                        </div>
                  </a>
              </li>
          </ul>
      </div>
  </div>
</template>
<script>
import GoodsHeader from './GoodsHeader'
export default {
  data() {
    return {
      title: "热评产品",
      hots: [
        {
          sourceUrl: "//www.mi.com/mituwatch/",
          imageUrl:
            "http://i3.mifile.cn/a4/1e737b55-91bd-4f5b-b085-405fa722142f",
          review: "很好，孩子很喜欢，产品不错",
          author: "showen",
          name: "米兔儿童电话手表",
          price: "299"
        },
        {
          sourceUrl: "//www.mi.com/mitu/",
          imageUrl:
            "http://i3.mifile.cn/a4/032d0ff1-f77f-4830-a469-f3564d55e0c5",
          review: "米兔真心不错！！内容丰富，声音柔和，孩子看见后，就抱着不撒手啦，超级喜欢！！！",
          author: "Jack伯爵",
          name: "米兔智能故事机",
          price: "199"
        },
        {
          sourceUrl: "//www.mi.com/note3/pro/",
          imageUrl:
            "http://i3.mifile.cn/a4/a14bd55a-2a7f-4e5f-9d8d-79e3e1bdb467",
          review: "手机很不错 外观大气金属质感 一直都用的红米手机 很不错 很漂亮也很好用",
          author: "1108656217",
          name: "红米Note 3全网通版",
          price: "899"
        },
        {
          sourceUrl: "//www.mi.com/miwifi3/",
          imageUrl:
            "http://i3.mifile.cn/a4/8949026b-fa9a-4370-989b-5d5e2f149106",
          review: "我就是喜欢这样的路由器，我每天回到家都要连着WiFi上网，上班就没办法连着呢！每次都等待着下班，我好...",
          author: "欧阳长",
          name: "小米路由器3",
          price: "149"
        }
      ]
    };
  },
  components: {
    "goods-header": GoodsHeader
  }
};
</script>
<style lang="scss" scoped>
.hotProduct{
    width: 1226px;
    height: auto;
    margin: 0 auto;
    .hot-wrap{
        .hot-content{
            display: flex;
            flex-flow: row nowrap;
            justify-content: space-between;
            .hot-item{
                background: #fff;
                width: 296px;
                height: 415px;
                transition: all .3s;
                &:hover{
                    transform: translateY(-3px);
                    box-shadow: 5px 5px 20px #ccc;
                }
                img{
                    width: 296px;
                    height: 220px;
                }
                .review-txt{
                    display: block;
                    color: #333;
                    height: 72px;
                    width: 240px;
                    margin: 20px auto ;
                    font-size: 14px;
                    font-weight: 400;
                    line-height: 24px;
                    overflow: hidden;
                }
                .review-author{
                    position: relative;
                    font-size: 12px;
                    height: 18px;
                    color: #b0b0b0;
                    margin: 0 28px 8px;
                    padding: 0 10px 0 0;
                }
                .item-desc{
                    margin-left: 30px;
                    font-size:14px;
                    font-weight: 400;
                    .item-name{
                        color: #333;
                    }
                    .sep{
                        margin: 0 4px;
                        color: #e0e0e0;
                    }
                    .item-price{
                        color: #ff6700;
                    }
                }
            }
        }
    }
}
</style>
