<template>
  <main>
    <!-- recupero l'emit da AlbumSelect e passo i dati alla funzione setCategorie  -->
    <AlbumSelect @SelectCategorie="setCategories" />
    <AlbumList :filter="FilterString" />
  </main>
</template>

<script>
  import AlbumList from './AlbumList.vue'
  import AlbumSelect from './AlbumSelect.vue'


  export default {
    name: 'MainDisk',
    components: {
      AlbumList,
      AlbumSelect,
    },
    data() {
      return {
        FilterString: '',
      }
    },

    methods: {

      setCategories: function( ...params ) {
        // console.log(stringInput, sec);
        console.log( ...params );
      }
    }
  }

</script>

<style scoped lang="scss">

</style>
