<template>
  <div class="container">
      <ul class="d-flex row mt-4">
          <li class="col-4 text-center" v-for="(movie, index) in movies" :key="index">
            <movies :movie="movie" />
          </li>
      </ul>
      <ul class="d-flex row mt-4">
		<li class="col-4 text-center" v-for="(serie, index) in series" :key="index">
			<movies :movie="serie"/>
		</li>
	</ul>
  </div>
</template>
<script>

import movies from './movies.vue';
export default {
    props: ['movies','series'],
    components: {
		movies
	}

}
</script>

<style lang="scss">
li {
    display: flex;
    color: white;
    background: rgb(163, 158, 158);
    justify-content: center;
    border: 1px solid rgb(0, 0, 0);
    margin-top: 10px
}



</style>