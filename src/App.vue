<template>
  <div id="app">
    <SiteHeader @searching="searchFilm" />
    <SiteMain :movies="movies"/>
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
    SiteMain
  },
  data(){
    return{
      movies: [],
    }
  },
  methods: {
    searchFilm() {
      axios
      .get()
        
      .then()
    }
  }
}
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap.scss";

</style>
