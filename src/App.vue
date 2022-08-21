<template>
  <div class="div">
    <BaseHeader :genres-list="genresList" @genre-change="setSelectedGenre"/>
    <BaseMain :selected-genre="selectedGenre"/>
  </div>
</template> 

<script>
import BaseHeader from './components/BaseHeader'
import BaseMain from './components/BaseMain.vue'
export default {
  name: "App",
  components: {
    BaseHeader,
    BaseMain,
  },
  data(){
    return{
      selectedGenre: '',
      genresList:['Rock','Metal','Pop']
    }
  },
  methods:{
    setSelectedGenre(genre){
       this.selectedGenre = genre;
    }
  }
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
