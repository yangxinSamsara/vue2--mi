<template>
  <div class="goods-smart">
    <div class="box">
        <div class="box-top clearfix">
            <h3>智能硬件</h3>
            <a href="javascript:;">
                <span class="top-sub">
                    查看全部
                    <i class="sub-icon fa fa-fw fa-chevron-circle-right"></i>
                </span>
            </a>
        </div>
        <div class="box-content clearfix">
            <div class="box-left">
                <a href="http://www.mi.com/scooter/">
                    <img src="http://i3.mifile.cn/a4/124d82cc-cfce-44ab-b711-28b21be81683" alt="">
                </a>
            </div>
            <div class="box-right">
                <ul class="box-list">
                    <li class="box-item" v-for="item in goods" :key="item.title">
                        <span class="discount-txt" :class="item.discountType">
                            {{item.discount}}
                        </span>
                        <a :href="item.sourceUrl">
                            <img :src="item.imgUrl" alt="">
                            <h3 class="title">{{item.title}}</h3>
                        </a>
                        <p class="desc">{{item.desc}}</p>
                        <p class="price">
                            ￥{{item.price}}元
                            <span class="old-price" v-if="item.discountType=='discount'">
                                ￥{{item.oldPrice}}元
                            </span>
                        </p>
                    </li>
                </ul>
            </div>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  data(){
      return{
        goods: [
            {sourceUrl: '//item.mi.com/1161200059.html', imgUrl: 'http://i3.mifile.cn/a4/T1rQAgB7Av1RXrhCrK.jpg', title: '小米路由器3', desc: '四天线设计，更安全更稳定', price: '149', discountType: 'free', discount: '免邮费'},
            {sourceUrl: '//www.mi.com/mibicycle/', imgUrl: 'http://i3.mifile.cn/a4/2b69b930-a2fd-4d09-a46a-8690cb79f764', title: '电助力折叠自行车', desc: '力矩传感电助力，让城市出行轻松有趣', price: '149', discountType: 'new', discount: '新品'},
            {sourceUrl: '//www.mi.com/mitu/', imgUrl: 'http://i1.mifile.cn/a1/pms_1464615180.86261317!220x220.jpg', title: '米兔智能故事机', desc: '能说会道，宝宝的好玩伴', price: '199', discountType: 'new', discount: '新品'},
            {sourceUrl: '//www.mi.com/water2/', imgUrl: '//i3.mifile.cn/a4/T1zTK_Bbhv1RXrhCrK.jpg', title: '小米净水器', desc: '厨下式 RO反渗透直出纯净水，包邮包安装', price: '1999'},
            {sourceUrl: '//www.mi.com/ihealth/ ', imgUrl: 'http://i1.mifile.cn/a1/T17FCQByWv1RXrhCrK!220x220.jpg', title: 'iHealth智能血压计（蓝牙版）', desc: '送给父母的健康礼物 测血压仅需1步', price: '199'},
            {sourceUrl: '//www.mi.com/dianfanbao/', imgUrl: 'http://i1.mifile.cn/a1/T1OVC_ByY_1RXrhCrK!220x220.jpg', title: '米家压力IH电饭煲', desc: '智能烹饪，3L 容量', price: '999'},
            {sourceUrl: '//item.mi.com/1163200015.html', imgUrl: 'http://i1.mifile.cn/a1/pms_1470730028.12443689!220x220.jpg', title: '全系智能套装限时款', desc: '开启你的智能生活', price: '292', oldPrice: '325', discountType: 'discount', discount: '享九折'},
            {sourceUrl: '//list.mi.com/accessories/tag?id=guangganban', imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99'}
        ]
      }
  }
}
</script>
<style lang="scss" scoped>
.goods-smart{
    width: 100%;
    height: auto;
    background: #F5F5F5;
    padding-top: 60px;
    margin-bottom: 26px;
}
.box{
    width: 1226px;
    margin: 0 auto;
    position: relative;
    .box-top{
        width: 100%;
        height: 58px;
        h3{
            margin: 0;
            float: left;
            font-size: 22px;
            line-height: 58px;
            font-weight: 200;
            color: #333;
        }
        .top-sub{
            float: right;
            display: block;
            font-size: 16px;
            line-height: 58px;
            color: #b0b0b0;
            cursor: pointer;
            &:hover{
                color: #ff6700;
                .sub-icon{
                    color: #ff6700;
                }
            }
            .sub-icon{
                color: #424242;
                font-size: 20px;
            }
        }
    }
}

.box-left{
    float: left;
    width: 234px;
    height: 614px;
    cursor: pointer;
    transition: all .5s;
    img{
        width: 100%;
        height: 614px;
    }
    &:hover{
        transform: translateY(-1px);
        box-shadow: 5px 5px 20px #5F5750;
    }
}

.box-right{
    background: red;
    float: left;
    width: 992px;
    height: 628px;
    .box-list{
        display: flex;
        flex-flow: row wrap;
        justify-content: flex-start;
        width: 100%;
        height: 100%;
        background: #f5f5f5;
        .box-item{
            position: relative;
            width: 234px;
            height: 260px;
            background: #fff;
            transition: all .5s;
            padding: 20px 0;
            margin:0 0 14px 14px;
            &:hover{
                transform:translateY(-1px);
                box-shadow: 5px 5px 20px #5F5750;
            }
            .discount-txt{
                position: absolute;
                top: 0;
                left: 50%;
                width: 64px;
                height: 20px;
                line-height: 20px;
                text-align: center;
                color: #fff;
                z-index: 4;
                margin-left: -32px;
                font-size: 12px;
                &.free{
                    background: #ffac13;
                }
                &.new{
                    background: #83c44e;
                }
                &.discount{
                    background: #e53935;
                }
            }
            img{
                display: block;
                width: 160px;
                height: 160px;
                margin: 0 auto;
            }
            .title{
                font-size: 14px;
                text-align: center;
                color: #333;
                font-weight: normal;
            }
            .desc{
                margin: 0 10px 10px;
                height: 18px;
                font-size: 12px;
                text-align: center;
                text-overflow: ellipsis;
                white-space: nowrap;
                overflow: hidden;
                color: #b0b0b0;
            }
            .price{
                color: #ff6700;
                font-size: 14px;
                text-align: center;
            }
            .old-price{
                color: #b0b0b0;
                text-decoration: line-through;
            }
        }
    }
}
</style>
