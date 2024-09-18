<template>
  <div class="home">
    <HeaderHome />
    <MainContentHome />
  </div>
</template>

<script>
import MainContentHome from './components/MainContentHome.vue'
import HeaderHome from './components/HeaderHome.vue'

export default {
  name: 'App',
  components: {
    MainContentHome,
    HeaderHome
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
