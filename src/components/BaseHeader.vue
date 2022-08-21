<template>
   <header class="d-flex justify-content-between align-center">
    <img class="img-fluid" src="../assets/img/spotify-logo.png" alt="spotify-logo" />
    <BaseSelect placeholder="Seleziona un genere" :options="genresList" @option-change="emitGenreChange" />  
  </header>
</template>

<script>
import BaseSelect from './BaseSelect.vue'
export default {
    name: 'BaseHeader',
    components:{
      BaseSelect
    },
    props:{
      genresList: Array
    },
    methods:{
      emitGenreChange(genre){
        this.$emit('genre-change', genre)
      }
    }

}
</script>

<style lang="scss" scoped>

   header {
  background-color: #2e3a46;
  img {
    width: 80px;
    padding: 10px;
  }
}
</style>