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
@import './assets/scss/common.scss';

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: "flow-circular", Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
  // margin-top: 60px;
}
</style>
