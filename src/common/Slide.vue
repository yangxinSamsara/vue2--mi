<template>
  <div class="banner">
     <el-carousel height='460px' arrow="never">
       <el-carousel-item v-for="item in banners" :key="item.imgUrl">
         <a :href="item.sourceUrl" target="_blank">
             <img :src="item.imgUrl" alt="">
         </a>
       </el-carousel-item>
     </el-carousel>
  </div>
</template>
<script>
export default {
 props:['banners']
 
}
</script>
<style lang="scss" scoped>

</style>
