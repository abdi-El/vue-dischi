<template>
    <header class="p-2"> 
        <img src="../assets/img/logo.png" alt="logo" class="h-100">    
    </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang='scss'>
    @import '@/styles/global';
    header{
        height: 80px;
        background-color: $secondary-color;
    }
</style>