<template>
  <div class="app">
    <myhead></myhead>
    <swiper></swiper>
    <collection></collection>
  </div>
</template>

<script>
import swiper from './components/Swiper.vue'
import myhead from './components/Header.vue'
import collection from './components/collection.vue'

export default {
  name:"app",
  components: {
    swiper,
    myhead,
    collection
  }
}
</script>

<style>
@import '../static/css/common.css';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
