<template>
  <div id="app">
    <div class="img"></div>
    <top-bar></top-bar>
    <top-header></top-header>
    <top-banner></top-banner>
    <top-sub></top-sub>
    <goods></goods>
    <mi-footer></mi-footer>
    <play-video :play-config="playConfig"></play-video>
  </div>
</template>

<script>
import bus from "./Bus";
import TopBar from "./components/TopBar";
import TopHeader from "./components/TopHeader";
import TopBanner from "./components/TopBanner";
import TopSub from "./components/TopSub";
import Goods from "./components/Goods";
import MiFooter from "./components/MiFooter";
import PlayVideo from "./common/PlayVideo";
export default {
  data() {
    return {
      playConfig: {}
    };
  },
  mounted() {
   this.recivePlayVideo()
  },
  methods:{
    recivePlayVideo(options){
      bus.$on('play',(options)=>{
        this.playConfig=options
      })
    }
  },
  name: "app",
  components: {
    "top-bar": TopBar,
    "top-header": TopHeader,
    "top-banner": TopBanner,
    "top-sub": TopSub,
    "goods": Goods,
    "mi-footer": MiFooter,
    "play-video": PlayVideo
  }
};
</script>

<style>
@import "./assets/css/base.css";
.img {
  background-image: url(./assets/images/topbar.jpg);
  background-repeat: no-repeat;
  background-position: center 0;
  max-width: 100%;
  height: 120px;
}
</style>
