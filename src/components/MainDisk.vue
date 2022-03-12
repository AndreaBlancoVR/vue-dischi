<template>
  <main>
    <!-- recupero l'emit da AlbumSelect e passo i dati alla funzione setCategorie  -->
    <AlbumSelect @SelectCategorie="setCategories" />
    <AlbumList :FilterStringFiglio="FilterStringPadre" />
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
        FilterStringPadre: '',
      }
    },

    methods: {
      // passo il valore recuperato dall'emit a FilterString
      setCategories: function( el ) {
        this.FilterStringPadre = el;
        // console.log(stringInput, sec);
        // console.log( ...params );
        console.log(this.FilterStringPadre)
      }
    }
  }

</script>

<style scoped lang="scss">

</style>
