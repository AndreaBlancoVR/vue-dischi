<template>
  <section>
      <div class="select-container">
            <!-- in questa select al change scateno la funzione emit -->
            <select name="category" @change="CategoriesFilter()" v-model="selected" id="category" aria-placeholder="Seleziona la categoria">
                <option value="" disabled selected hidden>Seleziona una categoria</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Rock">Rock</option>
                <option value="Metal">Metal</option>
            </select>
      </div>
  </section>
</template>

<script>
export default {
    data() {
        return {
            selected: '',
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
        background-color: #1E2D3B;
    }
</style>