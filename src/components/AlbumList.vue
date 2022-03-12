<template>
    <div class="row">
        <div class="container-master">
            <ul class="card-container">
                <AlbumCard v-for="(el, i) in filteredAlbums" :key="i" :album="el"></AlbumCard> 
            </ul>
            <div class="counter">
                <p>Ci sono {{ filteredAlbums.length}} album</p> 
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

    computed: {
        // creo una funzione che filtra album in base all'input inserito dall'utente
        filteredAlbums: function () {
            return this.albums.filter( (el) => {
                // funzione di callBack che effettua il controllo
                const { genre } = el
                return genre.toLowerCase().includes( this.FilterStringFiglio.toLowerCase() );
            } )
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
      height: calc(100vh - 200px);
      background-color: #1E2D3B;
      display: flex;
      justify-content: flex-start;
      align-items: center;
      flex-direction: column;

      #category {
          margin-top: 40px;
      }

      .container-master {
        flex-direction: column;
        width: 1160px;
        display: flex;

        .card-container {
        display: flex;
        padding: 77px 0;
        flex-wrap: nowrap;
        justify-content: center;
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