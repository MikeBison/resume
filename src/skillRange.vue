<template lang="html">
  <div class="skillRange">
    <div class='label'>
      <strong v-text="label"></strong>
    </div>
    <input type="range" :value="val" class="range" max="100" min="0" :disabled="ifDisable">
  </div>
</template>

<script>
export default {
  data(){
    return{

    }
  },
  props:[
    "label",
    "val",
    "ifDisable"
  ]
}
</script>

<style lang="less">
.skillRange{
.label{
  width:30%;
}
  .range{
    flex-grow: 1;
    background: rgba(60, 114, 230, .8);
    height: 18px;
    margin-top: 3px;
-webkit-border-radius: 5px;
-webkit-appearance: none !important;
  }
  .range::-webkit-slider-thumb{
    width: 28px;
    height: 18px;
    background: -webkit-gradient(
      linear,
      left top,
      left bottom,
      from(#fff),
      to(#ccc)
    );
    border: 1px solid #000;
    -webkit-box-shadow: 0 0 6px #000;
    -webkit-border-radius: 14px;
    -webkit-appearance: none !important;
  }
  strong,input{
    margin-left: 15px;
  }
  line-height: 24px;
  height: 24px;
  display: flex;
  margin-bottom: 10px;
}
.skillRange:first-child{
  margin-top: 10px;
}
</style>
