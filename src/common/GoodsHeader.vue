<template>
  <div class="header">
      <h2>{{title}}</h2>
  </div>
</template>
<script>
export default {
  props:['title']
}
</script>
<style lang="scss" scoped>
.header{
    position: relative;
    h2{
        margin: 0;
        font-size: 22px;
        font-weight: 200;
        line-height: 58px;
        color: #333;
    }
}
</style>
