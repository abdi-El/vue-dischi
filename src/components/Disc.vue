<template>
  <div class="text-center text-light">
      <img :src="img" :alt="title" class="w-100">
      <h5>{{title}}</h5>
      <h6 class="author">{{author}}</h6>
      <h6 class="date">{{date}}</h6>
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
        type: String,
        author: String,
    }
}
</script>

<style scoped lang='scss'>
    @import '@/styles/global';
    img{
        margin: 10px 0;
    }
    .author, .date{
        color: #6f7579;
    }
</style>