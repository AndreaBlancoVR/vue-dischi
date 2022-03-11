<template>
    <div class="row">
      <div class="container-master">
        <ul class="card-container">
          <li v-for="(el, i) in album" 
          :key="i" 
          class="card-wrapper">
              <div class="card-header">
                  <img class="aaa" src="https://www.dccomics.com/sites/default/files/styles/covers192x291/public/gn-covers/2019/04/CTWv1_CC_144-001_HD_5ca5299a751963.53054221.jpg?itok=ooPaoLDq" alt="">
              </div>
              <div class="card-footer">
                <h3>{{el.title}}</h3>
                <p>{{el.author}}</p>
                <p>{{el.year}}</p>
              </div>
          </li>
      </ul>
      <div class="counter">
      <p>Ci sono {{ album.length}} album</p> 
      </div>
      </div> 
    </div>
    
</template>

<script>
  import axios from 'axios'

  export default {
    name: 'AlbumList',
    data() {
        return {
            album: []
        }
    },
    methods: {
        fetchAlbums: function() {

            // richiamo la api
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then( res => {
                this.album = res.data.response
                console.log( res.data.response )  
            })

            // stampiamo eventuali errori
            .catch( err => {
                console.warn( err.data.response )
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
      background-color: #1E2D3B;
      display: flex;
      justify-content: center;

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

            .card-wrapper {
                display: flex;
                flex-direction: column;
                // width: calc(90% / 6);
                width: 200px;
                background-color: #2E3A46;
                // padding: 2%;
                padding: 20px;
                margin-bottom: 20px;

                .card-header {
                    width: 160px;
                    height: 160px;
                    // padding: 20px;
                    img {
                        width: 100%;
                        aspect-ratio: 1;
                    }

                }

                .card-footer {
                width: 160px;
                height: 160px;
                text-align: center;
                
                    h3 {
                        color: white;
                        text-transform: uppercase;
                        padding-top: 25px;
                        padding-bottom: 30px;
                    }

                    p {
                        color: #807E7C
                    }
                }
            }
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