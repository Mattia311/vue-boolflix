<template>
  <div class="SiteHeader text-center" >
      <input type="text" placeholder="Cerca un film" v-model="searchFilm" @keyup.enter="$emit('searching', searchFilm)">
      <button @click="$emit('searching', searchFilm)" >Search</button>
  </div>
</template>

<script>
export default {
    data() {
		return {
			searchFilm: ""
		}
	},
}
</script>

<style lang="scss">
input {
    width: 300px;
}

</style>