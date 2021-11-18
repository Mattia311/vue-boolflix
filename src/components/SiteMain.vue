<template>
  <div>
      <ul>
          <li  v-for="(movie, index) in movies" :key="index">
              <movies :movie="movie" />
          </li>
      </ul>
  </div>
</template>
<script>

import movies from './movies.vue';
export default {
    props: ['movies'],
    components: {
		movies
	}

}
</script>

<style>

</style>