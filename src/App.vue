<template>
  <div id="app">
    <HeaderDisk />
    <MainDisk />
  </div>
</template>

<script>
import HeaderDisk from './components/HeaderDisk.vue'
import MainDisk from './components/MainDisk.vue'

export default {
  name: 'App',
  components: {
    HeaderDisk,
    MainDisk,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
