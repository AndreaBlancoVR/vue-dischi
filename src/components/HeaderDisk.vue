<template>
  <header class="header">
    <figure class="logo">
      <img :src="require('../assets/img/' + logo) ">
    </figure>
  </header>
</template>

<script>
  export default {
    name: 'HeaderDisk',
    props: {
      logo: {
        type: String,
        default: 'logo-small.svg'
    }
  }
}
</script>

<style scoped lang="scss">

  .header {
    width: 100%;
    height: 70px;
    padding: 12px 0;
    background-color: #2E3A46;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    

    .logo {
      width: 45px;
      height: 45px;
      margin: 0 23px;

    }
  }

</style>
