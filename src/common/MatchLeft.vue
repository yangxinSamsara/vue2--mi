<template>
    <ul class="match-left">
        <li v-for="goods in leftGoods" :key="goods.imgUrl">
            <a :href="goods.sourceUrl">
                <img :src="goods.imgUrl" >
            </a>
        </li>
    </ul>
</template>
<script>
export default {
  props:['left-goods']
}
</script>

<style lang="scss">
.match-left{
    float: left;
    width: 234px;
    height: auto;
    li{
        width: 234px;
        height: 300px;
        margin-block-end: 14px;
        cursor: pointer;
        transition: all .3s;
        &:hover{
            transform: translateY(-2px);
            box-shadow: 5px 5px 20px #ccc;
        }
        img{
            width: 234px;
            height: 300px;
        }
    }
}
</style>