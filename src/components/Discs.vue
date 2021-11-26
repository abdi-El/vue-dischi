<template>
    <div class="container">
        <ul class="row" v-if="discsList != null">
            <div class="disc-container col-6 col-md-4 col-lg-2 my-3" v-for="disc in discsList" 
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


export default {
    name: 'Discs',
    components: {
        Disc,
        Loading,
    },
    props:{
        discsList: Array
    },
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