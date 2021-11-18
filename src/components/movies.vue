<template>
<div>
    <p>Titolo: {{movie.title}}</p>
	<p>Titolo originale: {{movie.original_title}}</p>
	<p>Lingua: {{movie.original_language}}</p>
	<p>Voto: {{movie.vote_average}}</p>
</div>
</template>

<script>
export default {

    props: ['movie']

}
</script>

<style>

</style>