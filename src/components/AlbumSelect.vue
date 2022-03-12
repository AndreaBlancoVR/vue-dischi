<template>
  <section>
      <div class="select-container">
            <!-- in questa select al change scateno la funzione emit -->
            <select name="category" @change="CategoriesFilter()" v-model="selected" id="category" aria-placeholder="Seleziona la categoria">
                <option value="" disabled selected hidden>Seleziona una categoria</option>
                <option value="0">Pop</option>
                <option value="1">Jazz</option>
                <option value="2">Rock</option>
                <option value="3">Classica</option>
            </select>
      </div>
  </section>
</template>

<script>
export default {
    data() {
        return {
            selected: '',
            filter: '',
        }
    },

    methods: {
        // creo funzione con comando emit da richiamare all'evento 
        CategoriesFilter: function() {
            this.$emit('SelectCategorie', this.selected)
        }
        
    }
}
</script>

<style>
    .select-container {
        height: 200px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>