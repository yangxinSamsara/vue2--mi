<template>
  <div class="video">
    <div class="header clearfix">
        <h2>{{title}}</h2>
        <a href="//www.mi.com/video/" target="_blank">
            <span class="look-all">
                查看全部
                <i class="sub-icon fa fa-fw fa-chevron-circle-right"></i>
            </span>
        </a>
    </div>
    <div class="video-content">
        <ul class="video-wrap clearfix">
            <li class="video-item"  v-for="item in videos" :key="item.desc"
                @click="playVideo(item)">
                <div class="figure">
                    <a href="javascript:void(0)">
                        <img :src="item.imgUrl" alt="">
                        <span class="play"><i class="fa fa-play"></i></span>
                    </a>
                </div>
                <h3 class="title">{{item.title}}</h3>
                <p class="vdesc">{{item.desc}}</p>
            </li>
        </ul>
    </div>
  </div>
</template>
<script>
import GoodsHeader from "./GoodsHeader";
import bus from '../Bus'
export default {
  data() {
    return {
      title: "视频",
      videos: [
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1ODg5ODA0MA==",
          imgUrl: "http://i3.mifile.cn/a4/73d67577-cbc7-4bd0-8678-4b1e95f4f4dc",
          title: "红米年度品牌视频",
          desc: "一亿人喜爱你，是一种责任。"
        },
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg3NjQ4OA==",
          imgUrl: "http://i3.mifile.cn/a4/f7e434fb-8ce4-4442-bf78-0d66e409dfc3",
          title: "小米笔记本Air最全介绍视频",
          desc: "带独立显卡的轻薄笔记本"
        },
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg4NjY0OA==",
          imgUrl: "http://i3.mifile.cn/a4/e2df3ad8-4147-44e1-8a54-b6bcafdc6c66",
          title: "小米笔记本Air可靠性测试视频",
          desc: "小米笔记本Air是如何炼成的？"
        },
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTU2NDM3NjEzMg==",
          imgUrl: "http://i3.mifile.cn/a4/T1v3LgBTxv1RXrhCrK.jpg",
          title: "小米Max 绝美外观视频",
          desc: '6.44" 大屏黄金尺寸，看什么都震撼'
        }
      ]
    };
  },
  methods:{
      playVideo(options){
          let videoOptions={
              status:true,
              title:options.title,
              videoUrl:options.videoUrl
          }
          bus.$emit('play',videoOptions)
      }
  }
};
</script>
<style lang="scss" scoped>
.video {
  width: 1226px;
  height: auto;
  margin: 0 auto;
}
.header {
  height: 58px;
  width: 100%;
  position: relative;
  h2 {
    margin: 0;
    padding: 0;
    font-size: 22px;
    font-weight: 200;
    color: #333;
    float: left;
    height: 58px;
    line-height: 58px;
  }
  .look-all {
    float: right;
    display: block;
    font-size: 16px;
    line-height: 58px;
    color: #424242;
    .sub-icon {
      font-size: 20px;
      color: #b0b0b0;
    }
    &:hover {
      color: #ff6700;
      .sub-icon {
        color: #ff6700;
      }
    }
  }
}
.video-wrap {
  width: 100%;
  position: relative;
  .video-item {
    float: left;
    width: 296px;
    height: 285px;
    margin: 0 0 14px 14px;
    background: #fff;
    transition: all 0.3s;
    &:hover {
      transform: translateY(-3px);
      box-shadow: 5px 5px 20px #ccc;
      .play {
        background: #ff6700;
      }
    }
    &:nth-child(1) {
      margin-left: 0;
    }
    .figure{
        position: relative;
        img{
            width: 296px;
            height: 180px;
        }
        .play{
            position: absolute;
            left: 20px;
            bottom: 10px;
            display: block;
            width: 32px;
            height: 20px;
            border: 2px solid #fff;
            color: #fff;
            border-radius: 12px;
            text-align: center;
        }
    }
    .title{
        font-size: 14px;
        font-weight: 400;
        color: #333;
        text-align: center;
        cursor: pointer;
        &:hover{
            color: #ff6700;
        }
    }
    .vdesc{
        font-size: 12px;
        color: #b0b0b0;
        text-align: center;
    }
  }
}
</style>
