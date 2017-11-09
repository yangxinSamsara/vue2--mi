<template>
  <div class="footer">
     <div class="footer-service">
       <ul class="service">
         <li>
           <span class="icon"><i class="fa fa-gavel"></i></span>
							1小时快修服务
         </li>
         <li>
           <span class="icon"><i class="fa fa-history"></i></span>
							7天无条件退货
         </li>
         <li>
           <span class="icon"><i class="fa fa-history"></i></span>
							15天免费换货
         </li>
         <li>
           	<span class="icon"><i class="fa fa-gift"></i></span>
							满150元包邮
         </li>
         <li>
           <span class="icon"><i class="fa fa-location-arrow"></i></span>
							520余家售后网点
         </li>
       </ul>
     </div>
     <div class="footer-links clearfix">
       <dl class="links">
         <dt>帮助中心</dt>
         <dd>账户管理</dd>
         <dd>购物指南</dd>
         <dd>订单操作</dd>
      </dl>
      <dl class="links">
         <dt>服务支持</dt>
         <dd>售后政策</dd>
         <dd>自助服务</dd>
         <dd>相关下载</dd>
      </dl>
      <dl class="links">
         <dt>线下门店</dt>
         <dd>小米之家</dd>
         <dd>服务网点</dd>
         <dd>零售网点</dd>
      </dl>
      <dl class="links">
         <dt>关于小米</dt>
         <dd>了解小米</dd>
         <dd>加入小米</dd>
         <dd>联系我们</dd>
      </dl>
      <dl class="links">
         <dt>关注我们</dt>
         <dd>新浪微博</dd>
         <dd>小米部落</dd>
         <dd>官方微信</dd>
      </dl>
      <dl class="links">
         <dt>特色服务</dt>
         <dd>F码通道</dd>
         <dd>礼物码</dd>
         <dd>防伪查询</dd>
      </dl>
      <div class="contact">
        <p class="tel">400-100-5678</p>
        <p>
          周一至周日 8:00-18:00 <br>
          （仅收市话费） 
        </p>
        <a href="javascript:;">
          <i class="fa fa-headphones"></i>24小时在线客服
        </a>
      </div>
     </div>
     <div class="site-info ">
       <div class="container clearfix">
         <div class="logo">小米官网</div>
         <div class="info-txt">
           <p class="sites">
             <a href="javascript:;">小米商城</a><span class="sep">|</span>
             <a href="javascript:;">MIUI</a><span class="sep">|</span>
             <a href="javascript:;">米聊</a><span class="sep">|</span>
             <a href="javascript:;">多看书城</a><span class="sep">|</span>
             <a href="javascript:;">小米路由器</a><span class="sep">|</span>
             <a href="javascript:;">视频电话</a><span class="sep">|</span>
             <a href="javascript:;">小米天猫店</a><span class="sep">|</span>
             <a href="javascript:;">小米淘宝直营店</a><span class="sep">|</span>
             <a href="javascript:;">小米网盟</a><span class="sep">|</span>
             <a href="javascript:;">小米移动</a><span class="sep">|</span>
             <a href="javascript:;">隐私政策</a><span class="sep">|</span>
             <a href="javascript:;">Select Region</a>
           </p>
           <p>
             <span>&copy;</span>
             <a href="javascript:;">mi.com</a>
             <span>京ICP证110507号</span>
             <a href="javascript:;">京ICP备10046444号</a>
             <a href="javascript:;">京公网安备11010802020134号</a>
             <a href="javascript:;">京网文[2014]0059-0009号</a>
             <br>
             违法和不良信息举报电话：185-0130-1238，本网站所列数据，除特殊说明，所有数据均出自我司实验室测试
          </p>
         </div>
         <div class="info-links">
           <a href="javascript:;"><img src="../assets/images/v-logo-1.png" alt=""></a>
           <a href="javascript:;"><img src="../assets/images/v-logo-2.png" alt=""></a>
           <a href="javascript:;"><img src="../assets/images/v-logo-3.png" alt=""></a>
           <a href="javascript:;"><img src="../assets/images/truste.png" alt=""></a>
         </div>
       </div>
       <div class="slogan">探索黑科技，小米为发烧而生</div>
     </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
.footer {
  width: 1226px;
  height: auto;
  margin: 0 auto;
  padding-bottom: 20px;
  .footer-service {
    padding: 27px 0;
    border-bottom: 1px solid #e0e0e0;
    .service {
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-around;
      li {
        display: block;
        font-size: 20px;
        color: #333;
        width: 210px;
        height: 25px;
        line-height: 25px;
        cursor: pointer;
        border-right: 1px solid #e0e0e0;
        &:nth-last-child(1) {
          border-right: 0;
        }
      }
    }
  }
  .footer-links {
    padding: 40px 0;
    .links {
      float: left;
      width: 160px;
      height: 122px;
      margin: 0;
      dt {
        margin: -1px 0 26px;
        font-size: 14px;
        line-height: 1.25;
        color: #424242;
      }
      dd {
        margin: 10px 0 0;
        font-size: 12px;
        color: #757575;
        cursor: pointer;
        &:hover {
          color: #ff6700;
        }
      }
    }
    .contact {
      float: right;
      width: 260px;
      height: 112px;
      border-left: 1px solid #e0e0e0;
      text-align: center;
      color: #616161;
      .tel {
        margin: 0 0 10px;
        color: #ff6700;
        font-size: 22px;
      }
      p {
        font-size: 12px;
        line-height: 16px;
        margin: 0 0 16px;
      }
      a {
        display: inline-block;
        width: 118px;
        height: 28px;
        color: #ff6700;
        border: 1px solid #ff6700;
        background: #fff;
        font-size: 12px;
        line-height: 28px;
        transition: all 0.4s;
        &:hover {
          background: #ff6700;
          color: #fff;
        }
      }
    }
  }
  .site-info {
    padding: 30px 0;
    font-size: 12px;
    background: #fafafa;
    .container {
      width: 1226px;
      margin: auto;
      .logo {
        float: left;
        width: 57px;
        height: 57px;
        display: block;
        text-align: left;
        text-indent: -9999px;
        overflow: hidden;
        margin-right: 10px;
        background: url(../assets/images/mi.png) no-repeat 50% 50%;
      }
      .info-txt {
        float: left;
        padding: 0;
        .sites {
          margin: 0;
          padding: 0;
          a {
            color: #757575;
            &:hover {
              color: #ff6700;
            }
          }
          .sep {
            color: #b0b0b0;
            margin: 0.28em;
            line-height: 18px;
          }
        }
        p {
          margin: 0;
          padding: 0;
          color: #b0b0b0;
          a {
            color: #b0b0b0;
            &:hover {
              color: #ff6700;
            }
          }
        }
      }
      .info-links {
        float: right;
        height: 28px;
        margin: 4px 0 0;
        img {
          width: auto;
          height: 28px;
          margin-left: 7px;
        }
      }
    }
    .slogan {
      width: 267px;
      height: 19px;
      margin: 30px auto 0;
      background: url(../assets/images/slogan.png) no-repeat center 0;
      text-align: left;
      text-indent: -9999px;
    }
  }
}
</style>
