<template>
<div class="sfondo">
  <div class="container">
      <ul class="d-flex row pt-4">
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
  background: gray;
  height: 100%;
}
.mt-4 {
    margin-top: 0px !important;
}

li {
    display: flex;
    color: white;
    background: rgb(163, 158, 158);
    justify-content: center;
    border: 1px solid rgb(0, 0, 0);
    margin-top: 10px
}



</style>