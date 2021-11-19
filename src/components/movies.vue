<template>
<div>
	<div class="">
       <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="">
    </div>
    <h2>Titolo: {{movie.title || movie.name}}</h2>
	<h4>Titolo originale: {{movie.original_title || movie.original_name}}</h4>
	<hr>
	<div>
        <span>Language: {{movie.original_language}}</span> <img class="flag" :src="flag(movie.original_language)">
    </div>
	<p>Voto: {{movie.vote_average}}</p>
</div>
</template>

<script>
export default {
	props: ['movie'],
	data() {
		return {
			noflag : ['gu', 'ii', 'ik', 'iu', 'jv', 'kg', 'ki', 'kj', 'ml', 'mr', 'nb', 'nd', 'ng', 'nn', 'nr', 'pi', 'ps', 'sa', 'sw', 'te', 'tl', 'tw'],
		}
	},
	
	methods:{
        flag(code) {
            if ( !this.noflag.includes(code) ) {
                return `https://www.unknown.nu/flags/images/${code}-100`;
            } else {
                return "https://upload.wikimedia.org/wikipedia/commons/2/2f/Missing_flag.png";
            }
        }
    },

}
</script>

<style lang="scss">
.flag {
	width: 30px;
}

</style>