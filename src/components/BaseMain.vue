<template>
  <div id="albums" class="container">
    <div class="albums-list row my-5">
      <div v-for="(album, id) in filteredAlbums" :key="id" :album="album" class="single-card p-3">
        <BaseCard
          :image="album.poster"
          :title="album.title"
          :author="album.author"
          :year="album.year"
        />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import BaseCard from './BaseCard.vue'
export default {
    name: 'BaseMain',
    components: {
        BaseCard,
    },
    props:{
      selectedGenre: String
    },
    data(){
        return{
            api: "https://flynn.boolean.careers/exercises/api/array/music",
            albums: []
        };
    },
        computed: {
        filteredAlbums() {
            if (!this.selectedGenre) return this.albums;

            return this.albums.filter((album) => album.genre === this.selectedGenre
            )
        },
    },
    methods:{
        getAlbums(){
            axios.get(this.api)
            .then((res) =>{
                this.albums = res.data.response
            })
        },
    },
    created() {
        this.getAlbums();
    }

}
</script>

<style lang="scss" scoped>
  .single-card{
    width: calc(100% / 4);
    
  }
</style>
