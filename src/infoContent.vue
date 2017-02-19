<template>
  <div class='info-content'>
    <strong v-text='label'></strong>
    <template v-if="isHref">
      <a :href="'http://'+content">
        <p v-text='content'></p>
      </a>
    </template>
    <template v-else>
      <p v-text="content"></p>
    </template>
  <div>
</template>

<script>
export default {
  name: "infoContent",
  data (){
    return {}
  },
  props:[
    'label',
    'content',
    "isHref"
  ]
}
</script>

<style>
  p,strong{
    line-height: 24px;
  }
  strong{
    float:left;
    margin-right: 8px
  }
  .info-content{
    margin-top: 10px;
    padding: 0px 10px;
    overflow: hidden;
  }
  .info-content:last-child{
    margin-bottom: 10px;
  }
  a{
    color:#096189;
    text-decoration: none;
  }
  a:hover{
    color:#0961ee
  }
</style>
