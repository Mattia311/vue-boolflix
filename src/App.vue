<template>
  <div id="app">
    <SiteHeader @searching="searchFilm" />
    <SiteMain :movies="movies" :series="series"/>
  </div>
</template>

<script>
import axios from 'axios';
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';

export default {
  name: 'App',
  components: {
    SiteHeader,
    SiteMain,
  },
  data(){
    return{
      movies: [],
      series:[],
    }
  },
  methods: {
    searchFilm(searchFilm) {
      axios
      .get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: '8dbd945848860b90e6916985f311d32e',
          query: searchFilm
          
        }
      })
      .then( (response) => {
        this.movies = response.data.results;
      });


      
      axios
      .get('https://api.themoviedb.org/3/search/tv', {
        params: {
          api_key: '8dbd945848860b90e6916985f311d32e',
          query: searchFilm
        }
      })
      .then( (response) => {
        this.series = response.data.results
      });
    }
      
    },
  
       
    
}
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap.scss";
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta2/css/all.min.css');

</style>
