<template>
  <div class="top-sub">
      <div class="sub-left">
          <ul class="channels">
              <li class="channel">
                  <a href="javascript:;">
                      <i class="fa fa-mobile fa-fw sub-icon"></i>
                      <p class="channel-txt">选购手机</p>
                  </a>
              </li>
              <div class="line-vertical"></div>
              <li class="channel">
                  <a href="javascript:;">
                      <i class="fa fa-gift fa-fw sub-icon"></i>
                      <p class="channel-txt">企业团购</p>
                  </a>
              </li>
              <div class="line-vertical"></div>
              <li class="channel">
                  <a href="javascript:;">
                      <i class="fa fa-refresh fa-fw sub-icon"></i>
                      <p class="channel-txt">官翻产品</p>
                  </a>
              </li>
              <div class="line-horizontal"></div>
              <div class="line-horizontal"></div>
              <div class="line-horizontal"></div>
              <li class="channel">
                  <a href="javascript:;">
                      <i class="fa fa-credit-card fa-fw sub-icon"></i>
                      <p class="channel-txt">小米移动</p>
                  </a>
              </li>
              <div class="line-vertical"></div>
              <li class="channel">
                  <a href="javascript:;">
                      <i class="fa fa-recycle fa-fw sub-icon"></i>
                      <p class="channel-txt">以旧换新</p>
                  </a>
              </li>
              <div class="line-vertical"></div>
              <li class="channel">
                  <a href="javascript:;">
                      <i class="fa fa-credit-card-alt fa-fw sub-icon"></i>
                      <p class="channel-txt">话费充值</p>
                  </a>
              </li>
          </ul>
      </div>
        <ul class="sub-right">
            <li>
                <a href="http://hd.mi.com/y/08191p/index.html" class="sub-item sub-2" target="_blank">
                <img src="http://i3.mifile.cn/a4/1327d707-4f67-4c36-8ae5-3d7704c989eb" alt="" />
                </a>
            </li>
            <li>
                <a href="http://item.mi.com/buyphone/redmipro/" class="sub-item sub-3" target="_blank">
                <img src="http://i3.mifile.cn/a4/c202123c-4197-4666-9793-2f1e156ab23a" alt="" />
                </a>
            </li>
            <li>
                <a href="http://item.mi.com/static/buymipad" class="sub-item sub-4" target="_blank">
                <img src="http://i3.mifile.cn/a4/216f7f38-66ee-4c1b-8409-8d77cb64d386" alt="" />
                </a>
            </li>
        </ul>
  </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss" scoped>
.top-sub{
    position: relative;
    width: 1226px;
    margin: 14px auto 26px;
    height: auto;
}
.sub-left{
    float: left;
    width: 234px;
    height: 170px;
    background: #5f5750;
}

.channels{
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    align-items: flex-start;
    padding: 3px;
    .channel{
        width: 74px;
        height: 82px;
        cursor: pointer;
        &:hover{
            .channel-txt{
                color: #fff;
            }
            .sub-icon{
                color: #fff;
            }
        }
        .channel-txt{
            display: block;
            margin: 0;
            width: 75px;
            font-size: 12px;
            text-align: center;
            color: rgba(255,255,255,0.7);
        }
        .sub-icon{
            width: 75px;
            height: 23px;
            margin-top: 18px;
            margin-bottom: 5px;
            font-size: 20px;
            color: rgba(255,255,255,0.7);
        }
    }
    .line-vertical{
        width: 1px ;
        height: 60px;
        margin-top: 10px;
        background: rgba(255,255,255,0.1);
    }
     .line-horizontal{
        width: 60px ;
        height:1px;
        margin: 0 8px;
        background: rgba(255,255,255,0.1);
    }
}

.sub-right{
    display: flex;
    flex-flow: row nowrap;
    justify-content: flex-start;
    li{
        width: 316px;
        height: 170px;
        margin-left: 15px;
    }
    .sub-item{
        display: block;
        transition: all .3s;
        &:hover{
            box-shadow: 0 5px 30px #ccc;
        }
        img{
            width: 316px;
            height: 170px;
        }
    }
}
</style>
