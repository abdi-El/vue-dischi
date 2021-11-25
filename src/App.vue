<template>
  <div id="app">
    <Header />
    <main>
      <Discs />
    </main>
  </div>
</template>

<script>
// imports
import Header from '@/components/Header.vue'
import Discs from '@/components/Discs.vue'

export default {
  name: 'App',
  components: {
    Header,
    Discs,
  }
}
</script>

<style lang="scss">
  @import '@/styles/global';
  #app{
    background-color: $main-color;
    height: 100%;
    main{
      background-color: $main-color;
    }
  }
</style>
