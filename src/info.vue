<template>
  <div class='info-block'>
    <img v-if="imgSrc" :src="imgSrc">
    <h5 v-text='title' v-bind:class="{ weight: !notBold}"></h5>
    <div class='line' v-if="!hideline"></div>
  </div>
</template>

<script>
export default {
  name: "info",
  data() {
    return{

    };
  },
  props: [
    'imgSrc',
    'title',
    'hideline',
    'notBold'
  ]
}
</script>

<style lang='less'>
    .info-block {
      img,h5,.line {
        float:left;
        margin-left: 10px;
      }
      img{
        height: 50px;
      }
      h5{
        line-height: 50px;
      }
      .weight{
        font-weight: bold;
      }
      .line{
        border-top: 2px solid #000;
        margin-top: 25px;
        flex-grow: 1
      }
      overflow: hidden;
      display: flex;
    }
</style>
