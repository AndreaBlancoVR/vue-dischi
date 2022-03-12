<template>
    <div class="row">
        <div class="container-master">
            <ul class="card-container">
                <AlbumCard v-for="(el, i) in albums" :key="i" :album="el"></AlbumCard> 
            </ul>
            <div class="counter">
                <p>Ci sono {{ albums.length}} album</p> 
            </div>
        </div> 
    </div>
    
</template>

<script>
    import axios from 'axios'
    import AlbumCard from './AlbumCard.vue'

  export default {
    components: {
        AlbumCard,
    },

    data() {
        return {
            albums: [],
        }
    },

    props: {
        FilterStringFiglio: {
            type: String,
            default: ''
        }
    },



    methods: {
        fetchAlbums: function() {

            // richiamo la api
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then( res => {
                this.albums = res.data.response
                console.log( res.data.response )  
            })

            // stampiamo eventuali errori
            .catch( err => {
                console.warn( err.response )
            })
        }
    },
    // richiamo la funzione
    created() {
        this.fetchAlbums()
    }
}
</script>

<style scoped lang="scss">

    .row {
      width: 100%;
      height: 100vh;
      background-color: #1E2D3B;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;

      #category {
          margin-top: 40px;
      }

      .container-master {
        flex-direction: column;
        max-width: 1160px;
        display: flex;

        .card-container {
        display: flex;
        padding: 77px 0;
        flex-wrap: nowrap;
        justify-content: flex-start;
        gap: 3%;
        flex-wrap: wrap;

        }
        .counter {
                align-items: center;
                align-self: center;
                padding-bottom: 30px;
                color: white;
        }
      }
    }
</style>