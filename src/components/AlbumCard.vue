<template>
    <li class="card-wrapper">
        <div class="card-header">
            <img :src="album.poster">
        </div>
        <div class="card-footer">
            <h3>{{album.title}}</h3>
            <p>{{album.author}}</p>
            <p>{{album.year}}</p>
        </div>
    </li>
  
</template>

<script>
  export default {
    props: {
        album: {
            type: Object,
            required: true,
        }
    }
  }

</script>

<style scoped lang="scss">
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
                    cursor: pointer;
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
                        cursor: pointer;
                    }

                    p {
                        color: #807E7C;
                        cursor: pointer;
                    }
                }
            }
</style>