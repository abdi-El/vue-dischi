<template>
    <header class="p-2 d-flex justify-content-between"> 
        <img src="../assets/img/logo.png" alt="logo" class="h-100">
        <select class="w-25" @change="$emit('genereSelected', selected)" v-model="selected">
            <option value="">&#10140; all genres</option>
            <option v-for='(genere, index) in genereList' :key='genere[index]' :value="genere">{{genere}}</option>
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
    props:{
        genereList: Array
    },
}
</script>

<style scoped lang='scss'>
    @import '@/styles/global';
    header{
        height: 70px;
        background-color: $secondary-color;
        select{
            background-color: $main-color;
            border-radius: 10px;
            border: none;
            color: white;
            transition: scale 0.1s;
            &:hover{
                    cursor: pointer;
                }
            option{
                box-shadow: 5px 5px rgba(0,0,0,1);
            }
        }
    }
</style>