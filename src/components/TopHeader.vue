<template>
  <div class="top-header">
      <div class="container">
          <a href="javascript:;" class="mi"></a>
          <a href="javascript:;" class="gif"></a>
          <div class="header-navs">
              <ul class="navs">
                  <li class="nav" v-for="item in navs" :key="item.name">
                      <template v-if="item.type">
                          <a href="javascript:;" class="nav-item" 
                            @mouseenter="headerEnter(item.type)"
                            @mouseleave="headerLeave()">
                              {{item.name}}
                          </a>
                      </template>
                      <template v-else>
                          <a :href="item.sourceUrl" class="nav-item">
                              {{item.name}}
                          </a>
                      </template>
                  </li>
              </ul>
          </div>
          <div class="header-search">
              <input @focus="iptFocus" @blur="iptBlur" type="search" name="search" class="search-ipt">
              <label for="search" class="search-btn">
                  <i class="icon-search"></i>
              </label>
              <ul class="hot-word" v-show="hotStatus">
                <li class="hot-item" v-for="item in hotItems" :key="item">
                    {{item}}
                </li>
              </ul>
              <ul class="search-result clearfix">
                <li v-for="item in results" :key="item.name">
                  <span class="item-name">{{item.name}}</span>
                  <span class="item-num">约有{{item.number}}件</span>
                </li>
              </ul>
          </div>
      </div>
      <transition name="fade">
        <div class="header-menu" v-show="headerStatus"
            @mouseenter="headerEnter()"
            @mouseleave="headerLeave()">
          <ul class="menus clearfix">
            <li class="product" v-for="item in currentPhones" :key="item.name">
              <a :href="item.sourcePath">
                <img :src="item.imgUrl" class="product-img">
              </a>
              <div class="product-name">{{item.name}}</div>
              <div class="product-price">{{item.price}}</div>
            </li>
          </ul>
        </div>
      </transition>
  </div>
</template>
<script>
export default {
  data() {
    return {
      hotStatus: true,
      headerStatus: false,
      tids: "",
      currentPhones: '',
      hotItems: ["红米pro", "小米笔记本air"],
      xiaomi: [
        {
          name: "小米Max",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/maxdingbu!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1299元起"
        },
        {
          name: "小米手机5",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/mi5!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1499元起"
        },
        {
          name: "小米手机4c",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mi4c!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1099元"
        }
      ],
      red: [
        {
          name: "红米pro",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/hongmipro-320!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1499元起"
        },
        {
          name: "红米note3",
          imgUrl: "http://c1.mifile.cn/f/i/g/2015/video/hongmi3s!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "899元起"
        },
        {
          name: "红米手机3S",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/note3!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "699元起"
        },
        {
          name: "红米手机3",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hongmi3!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "699元起"
        },
        {
          name: "红米手机3X",
          imgUrl: "http://c1.mifile.cn/f/i/g/doodle/320-220!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "799元"
        }
      ],
      flats: [
        {
          name: "小米平板2 64GB",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mipad2-64!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1299元"
        },
        {
          name: "小米平板2 64GB Windows版",
          imgUrl:
            "http://c1.mifile.cn/f/i/15/goods/nav/mipad2-64-win!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1299元"
        },
        {
          name: "小米笔记本Air 12.5",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/video/bijiben32012.5!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "3499元"
        },
        {
          name: "小米笔记本Air 13.3",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben320!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "4999元"
        }
      ],
      tv: [
        {
          name: "小米电视3S 43英寸",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-43!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3s/43/",
          price: "1499元"
        },
        {
          name: "小米电视3S 48英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv3s48!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3s/48/",
          price: "1999元"
        },
        {
          name: "小米电视3 55英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv355!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3/55/",
          price: "3299元起"
        },
        {
          name: "小米电视3 60英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv3-60!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3/60/",
          price: "3499元"
        },
        {
          name: "小米电视3S 65英寸 曲面",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-65!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "8999元"
        },
        {
          name: "小米电视3 70英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv70!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3/70/",
          price: "8999元"
        }
      ],
      box: [
        {
          name: "小米盒子mini版",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hezimini.png",
          sourcePath: "http://www.mi.com/hezimini/",
          price: "179元"
        },
        {
          name: "小米盒子3",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hezi3.png",
          sourcePath: "http://www.mi.com/hezi3/",
          price: "249元"
        },
        {
          name: "小米盒子3 增强版",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hezi3s!160x110.jpg",
          sourcePath: "http://www.mi.com/hezi3s/",
          price: "399元"
        },
        {
          name: "小米电视主机",
          imgUrl: "http://c1.mifile.cn/f/i/g/2015/cn-index/zhuji!160x110.jpg",
          sourcePath: "http://www.mi.com/tvzj/",
          price: "999元"
        },
        {
          name: "小米家庭音响 金属版",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/jinshuban!160x110.jpg",
          sourcePath: "http://item.mi.com/1160800073.html",
          price: "899元"
        },
        {
          name: "小米家庭音响 标准版",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/putonban!160x110.jpg",
          sourcePath: "http://item.mi.com/1160800074.html",
          price: "699元"
        }
      ],
      router: [
        {
          name: "小米路由器 3",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/miwifi-3!160x110.jpg",
          sourcePath: "http://www.mi.com/miwifi3/",
          price: "149元"
        },
        {
          name: "小米路由器 mini",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/miwifimini!160x110.jpg",
          sourcePath: "http://www.mi.com/miwifimini/",
          price: "119元"
        },
        {
          name: "小米路由器 青春版",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/miwifilite!160x110.jpg",
          sourcePath: "http://www.mi.com/miwifilite/",
          price: "69元"
        },
        {
          name: "小米WiFi放大器",
          imgUrl:
            "http://c1.mifile.cn/f/i/15/goods/nav/wifiExtension!160x110.jpg",
          sourcePath: "http://item.mi.com/1153200003.html",
          price: "35元"
        }
      ],
      hardware: [
        {
          name: "九号平衡车",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/scooter!160x110.jpg",
          sourcePath: "http://www.mi.com/scooter/",
          price: "1999元"
        },
        {
          name: "小米净水器",
          imgUrl: "http://c1.mifile.cn/f/i/g/2015/cn-index/water2!160x110.jpg",
          sourcePath: "http://www.mi.com/water/",
          price: "1299元起"
        },
        {
          name: "米家压力IH电饭煲",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/dianfanbao!160x110.jpg",
          sourcePath: "http://www.mi.com/dianfanbao/",
          price: "999元"
        },
        {
          name: "小米空气净化器 2",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/air2!160x110.jpg",
          sourcePath: "http://www.mi.com/air2/",
          price: "649元"
        },
        {
          name: "智能摄像机",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/doodle/zhinengyingjian!160x110.jpg",
          sourcePath: "http://list.mi.com/accessories/tag?id=shexiangji",
          price: "149元起"
        }
      ],
      navs: [
        { name: "小米手机", type: "xiaomi" },
        { name: "红米", type: "red" },
        { name: "平板 · 笔记本", type: "flats" },
        { name: "电视", type: "tv" },
        { name: "盒子 · 影音", type: "box" },
        { name: "路由器", type: "router" },
        { name: "智能硬件", type: "hardware" },
        { name: "服务", sourceUrl: "//www.mi.com/service/" },
        { name: "社区", sourceUrl: "http://www.xiaomi.cn" }
      ],
      results: [
        { name: "小米手机5", number: "11" },
        { name: "空气净化器2", number: "1" },
        { name: "活塞耳机", number: "4" },
        { name: "小米路由器", number: "8" },
        { name: "移动电源", number: "21" },
        { name: "运动相机", number: "3" },
        { name: "小米摄像机", number: "2" },
        { name: "小米体重秤", number: "1" },
        { name: "小米插线板", number: "13" },
        { name: "配件优惠套装", number: "32" }
      ]
    };
  },
  methods: {
    iptFocus() {
      $(".header-search").addClass("search-active");
      $(".search-result").slideDown();
      this.hotStatus = false;
    },
    iptBlur() {
      $(".header-search").removeClass("search-active");
      $(".search-result").slideUp();
      this.hotStatus = true;
    },
    headerEnter(type) {
      if (type) {
        this.currentPhones = this[type];
      }
      this.headerStatus = true;
      clearTimeout(this.tids);
    },
    headerLeave() {
      let self = this;
      this.tids = setTimeout(function() {
        self.headerStatus = false;
      }, 300);
    }
  }
};
</script>
<style lang="scss" scoped>
.top-header {
  width: 100%;
  height: 100px;
}

.container {
  position: relative;
  display: flex;
  flex-flow: row nowrap;
  justify-content: flex-start;
  align-items: center;
  width: 1226px;
  height: 100%;
  margin: 0 auto;
}

.mi {
  width: 55px;
  height: 55px;
  background: url(../assets/images/mi.png) no-repeat;
  background-size: 100% 100%;
}

.gif {
  width: 80px;
  height: 80px;
  margin-left: 30px;
  background: url(../assets/images/timg.gif) no-repeat;
  background-size: 100% 100%;
}

.header-navs {
  position: relative;
  margin-left: 70px;
}

.navs {
  height: 88px;
  line-height: 88px;
  .nav {
    display: inline-block;
    .nav-item {
      display: block;
      height: 88px;
      line-height: 88px;
      font-size: 16px;
      padding: 0 10px;
      color: #333;
      &:hover {
        color: #ff6700;
      }
    }
  }
}

.header-search {
  position: absolute;
  top: 23px;
  right: 0;
  width: 295px;
  height: 50px;
  border: 1px solid #e0e0e0;
  .search-ipt {
    float: left;
    width: 240px;
    height: 100%;
    border: 0;
    outline: none;
  }
  .search-btn {
    display: block;
    float: right;
    width: 50px;
    height: 100%;
    border-left: 1px solid #e0e0e0;
    cursor: pointer;
    .icon-search {
      display: block;
      width: 20px;
      height: 20px;
      background: url(../assets/images/icon-search1.png) center center no-repeat;
      background-size: 100% 100%;
      margin: 15px;
    }
    &:hover {
      background: #ff6700;
      .icon-search {
        background: url(../assets/images/icon-search2.png) center center
          no-repeat;
        background-size: 100% 100%;
      }
    }
  }
  .hot-word {
    position: absolute;
    top: 14px;
    right: 60px;
    z-index: 2;
    text-align: right;
    .hot-item {
      float: left;
      height: 18px;
      line-height: 18px;
      padding: 0 5px;
      font-size: 12px;
      background: #eee;
      color: #757575;
      margin-right: 5px;
      cursor: pointer;
      &:hover {
        color: #fff;
        background: #ff6700;
      }
    }
  }

  .search-result {
    border: 1px solid #ff6700;
    display: none;
    position: absolute;
    left: -1px;
    top: 50px;
    width: 244px;
    height: auto;
    background: #fff;
    z-index: 20;
    li {
      padding: 6px 12px;
      width: 100%;
      height: 30px;
      box-sizing: border-box;
      cursor: pointer;
      .item-name {
        float: left;
        font-size: 12px;
      }
      .item-num {
        float: right;
        font-size: 10px;
        color: #b0b0b0;
      }
    }
  }
}

.search-active {
  border: 1px solid #ff6700;
  .search-btn {
    border-left: 1px solid #ff6700;
  }
}
.header-menu {
  position: absolute;
  left: 0;
  top: 260px;
  width: 100%;
  height: 230px;
  background: #fff;
  box-shadow: 0 1px 5px #ccc;
  z-index: 11;
  .menus {
    list-style: none;
    margin: 0 auto;
    padding: 30px 0 0 250px;
    width: 1500px;
    .product {
      float: left;
      a {
        display: block;
        padding: 0 30px;
        border-right: 1px solid #ccc;
      }
      &:nth-last-child(1) {
        a {
          border-right: 0;
        }
      }
      .product-img {
        width: 100%;
        width: 160px;
        height: 110px;
      }
      .product-name {
        width: 100%;
        height: 16px;
        margin-top: 16px;
        font-size: 12px;
        text-align: center;
      }
      .product-price {
        width: 100%;
        height: 14px;
        margin-top: 10px;
        font-size: 10px;
        text-align: center;
        color: #ff6700;
      }
    }
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease;
  opacity: 1;
  height: 235px;
}
.fade-enter,
.fade-leave-active {
  height: 0;
  opacity: 0;
}
</style>
