<template>
<div class="d-flex justify-content-between header">
  <div class="Sitebar">
    <img class="logo" src="https://www.ailequal.com/ajax-ex-boolflix/img/boolflix.png" alt="">
  </div>
  <div class="SiteHeader text-center" >
      <i class="fas fa-search" @click="$emit('searching', searchFilm)"></i>
      <input type="text" placeholder="Cerca un film" v-model="searchFilm" @keyup.enter="$emit('searching', searchFilm)">
      <button @click.prevent="resetSearch()">Clear</button>
  </div>
</div>
</template>

<script>
export default {
  data() {
		return {
			searchFilm: ""
		}
	},
  methods : {
    resetSearch() {
            this.searchFilm = '';
            this.$emit('search', this.searchFilm);
        }

  }
}
</script>

<style lang="scss">
.header {
  background: black;
  .logo {
    width: 200px;
  }
  .SiteHeader {
    margin-top: 25px;
    
    input {
      width: 400px;
    }
    i {
      background: white;
      width: 34px;
      height: 28px;
      padding-top: 6px;
      color: gray;
      cursor: pointer;
    }
    button {
      margin-right: 50px;
      background: white;
      border: none;
      height: 28px;
    }
  }
}

</style>