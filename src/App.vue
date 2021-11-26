<template>
  <div id="app">
    <Header @genereSelected='genereSelected'/>
    <main>
      <Discs  :discsList='filteredSongs'/>
    </main>
  </div>
</template>

<script>
// imports
import Header from '@/components/Header.vue'
import Discs from '@/components/Discs.vue'
import axios from 'axios';

export default {
  name: 'App',
  data(){
    return{
      discsList: null,
      genere: '',
    }
  },
  components: {
    Header,
    Discs,
  },
  methods:{
    getSongs(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(result=>{
                    this.discsList=result.data.response
                })
    },
    genereSelected(selected){
      this.genere=selected
    }
  },
  created(){
    this.getSongs()
  },
  computed:{
    filteredSongs(){
      if(this.genere == ''){
        return this.discsList
      }
      else{
        return this.discsList.filter(element=>element.genre == this.genere)  
      }
    },
  }
}
</script>

<style lang="scss">
  @import '@/styles/global';
  #app{
    background-color: $main-color;
    main{
      background-color: $main-color;
    }
  }
</style>
