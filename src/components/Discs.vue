<template>
    <div class="container">
        <ul class="row" v-if="this.discsList != null">
            <div class="disc-container col-6 col-md-4 col-lg-2 my-3" v-for="disc in this.discsList" 
                :key='`${disc.title}`'>
                <Disc  
                    class="disc p-3 h-100"
                    :img="disc.poster"
                    :title="disc.title"
                    :author="disc.author"
                    :date="disc.year"
                    :type="disc.genre"
                    />
            </div>
        </ul>
        <div v-else>
            <Loading/>
        </div>
    </div>
</template>

<script>
import Disc from '@/components/Disc.vue';
import Loading from '@/components/Loading.vue';
import axios from 'axios';

export default {
    name: 'Discs',
    components: {
        Disc,
        Loading,
    },
    data(){
        return{
            discsList: null,
        }
    },
    created(){
        this.getSongs();
    },
    methods:{
        getSongs(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(result=>{
                    this.discsList=result.data.response
                })
        }
    }
}
</script>

<style scoped lang='scss'>
    @import '@/styles/global';
    ul{
        justify-content: center;
    }
    .disc {
        background-color: $secondary-color;
    }
</style>