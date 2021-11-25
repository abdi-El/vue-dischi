<template>
  <div class="text-center text-light">
      <img :src="img" :alt="title" class="w-100">
      <h5>{{title}}</h5>
      <h5>{{date}}</h5>
      <h6>{{type}}</h6>
  </div>
</template>

<script>
export default {
    name: 'Disc',
    props:{
        img: String,
        title: String,
        date: String,
        type: String
    }
}
</script>

<style scoped lang='scss'>
    img{
        margin: 10px 0;
    }
</style>