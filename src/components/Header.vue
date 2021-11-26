<template>
    <header class="p-2 d-flex justify-content-between"> 
        <img src="../assets/img/logo.png" alt="logo" class="h-100">
        <select class="w-25" @change="$emit('genereSelected', selected)" v-model="selected">
            <option value="">Select</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Metal">Metal</option>
            <option value="Jazz">Jazz</option>
        </select>   
    </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            selected:'',
        }
    },
    methods:{
        logLog(){
            console.log(this.selected)
        }
    }
}
</script>

<style scoped lang='scss'>
    @import '@/styles/global';
    header{
        height: 80px;
        background-color: $secondary-color;
    }
</style>