<template>
  <div class="video-mask" v-show="maskStatus">
    <transition name="fade">
        <div class="video-content" v-show="videoStatus">
            <div class="video-header clearfix">
                <h3 class="title-txt">{{playConfig.title}}</h3>
                <div class="cancel" @click="cancel">
                    <i class="cancel-btn fa fa-times"></i>
                </div>
            </div>
            <div class="video">
                <iframe width="880" height="536"  :src="playConfig.videoUrl" frameborder="0"></iframe>
            </div>
        </div>
    </transition>
  </div>
</template>
<script>
import bus from "../Bus";
export default {
  data() {
    return {
      maskStatus: false
    };
  },
  props: ["playConfig"],
  computed: {
    videoStatus() {
      return this.playConfig.status;
    }
  },
  watch: {
    videoStatus(newVal, oldVal) {
      const that = this;
      if (!newVal) {
        setTimeout(function() {
          that.maskStatus = that.videoStatus;
        }, 500);
      } else {
        that.maskStatus = that.videoStatus;
      }
    }
  },
  methods: {
    cancel() {
      this.playConfig.status = false;
      this.playConfig.videoUrl = "";
    }
  }
};
</script>
<style lang="scss" scoped>
.video-mask {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: #000;
  z-index: 12;
}
.video-content {
  position: absolute;
  top: 300px;
  left: 50%;
  margin-left: -440px;
  width: 880px;
  height: 596px;
  background: #fff;
  .video-header {
    padding: 14px 20px;
    background: #fff;
    .title-txt {
      margin: 0;
      font-size: 20px;
      font-weight: 400;
      line-height: 32px;
      color: #424242;
    }
    .cancel {
      display: block;
      position: absolute;
      top: 10px;
      right: 20px;
      width: 30px;
      height: 30px;
      line-height: 30px;
      text-align: center;
      border-radius: 30px;
      font-size: 24px;
      color: #757575;
      transition: all 0.3s;
      cursor: pointer;
      &:hover {
        color: #fff;
        background: #e53935;
      }
    }
  }
  .video {
    width: 880px;
    height: 536px;
  }
}

.fade-enter-active,.fade-leave-active{
    transition:  all .3s ease-out;
    transform: translateY(30%)
}
.fade-enter,.fade-leave-active{
    transform: translateY(-100%)
}
</style>
