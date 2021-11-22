<template>
<div class="sfondo">
  <div class="container">
    <h2 class="text-center">FILM:</h2>
      <ul class="d-flex row">
          <li class="col-4 text-center" v-for="(movie, index) in movies" :key="index">
            <movies :movie="movie" />
          </li>
      </ul>
      <h2 class="text-center">SERIE:</h2>
      <ul class="d-flex row pt-4">
		<li class="col-4 text-center" v-for="(serie, index) in series" :key="index">
			<movies :movie="serie"/>
		</li>
	</ul>
  </div>

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
.sfondo {
  background: rgb(66, 64, 64);
  height: 100%;
}

li {
    display: flex;
    color: white;
    background: rgb(66, 64, 64);
    justify-content: center;
    border: none;
    margin-top: 10px;
    height: 515px;
    margin-bottom: 50px;
}
h2 {
  color: red;
  background: black;
  width: 200px;
}



</style>