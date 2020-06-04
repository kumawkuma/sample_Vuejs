<template>
  <div id="button">
    <button @click="countUp">{{message}} {{count}}</button>
  </div>
</template>

<script>
export default {
  name: "likeButton",
  props:{
      message:{
        type:String,
        default:'Good'
      }  
    },
  data:function(){
    return{
      count: 0
    }
  },
  methods:{
      countUp(){
          this.count++;
          this.$emit('increment');
      }
  }
}
</script>

<style>
#button{
    margin: 0 auto;
    padding-bottom: 14px;
    font-family: serif;
    width: 50pxpx;

}


</style>