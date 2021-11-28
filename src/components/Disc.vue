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
    div{
        border-radius: 10px;
        transition: scale 0.1s, box-shadow 0.1s;
        &:hover{
            scale: 1.03;
            cursor: pointer;
            box-shadow: 5px 5px 2px rgba(0,0,0,0.2);
        }
        &:active{
            scale: 1;
            cursor: pointer;
            box-shadow:none;
        }
        img{
            margin: 10px 0;
        }
        h6:hover{
            color: $main-color;
        }
        .author, .date{
            color: #6f7579;
        }
    }
</style>