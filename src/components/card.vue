<template>
  <article>
    <img :src="picture.url" alt="">
  </article>
</template>

<script>
export default {
  name: 'card',
  props:{
    picture:String
  }

}
</script>

<style>
  article{
    width:300px;
    height:300px;
    background-color: #1E1D28;
    border-radius: 20px;
    margin:30px 30px 30px 0;
  }
  img{
    width:300px;
    height:300px;
    border-radius: 20px;
  }
</style>