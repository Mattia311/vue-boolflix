<template>
<div class="movies">
	<div class="">
       <img class="img_copertina" :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="">
    </div>
    <div class="hover">
    <p class="titolo1"><strong>Titolo:</strong>{{movie.title || movie.name}}</p>
	<p class="titolo2"><strong>Titolo originale:</strong>{{movie.original_title || movie.original_name}}</p>
	<div class="lenguage">
        <span><strong>Lenguage:</strong> {{movie.original_language}}</span> <img class="flag" :src="flag(movie.original_language)">
    </div>
    <div class="voto">
        <p><strong>Voto:</strong><i v-for="n in 5" :key="n" class="fa-star" :class="(n <= vote(movie.vote_average)) ? 'fas' : 'far'"></i></p>
    </div>
    <div class="overview text-start">
        <p><strong>Overview:</strong> {{movie.overview}}</p>
    </div>

    </div>
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
        },
        vote(num){
            num = (num/2);
            return num = Math.ceil(num)
        }
    },

}
</script>

<style lang="scss">
.movies {
    position: relative;
}
.img_copertina {
    background: gray;
    border: 3px solid white;
}
.lenguage {
    position: absolute;
    bottom: -29px;
    margin-left: 13px;
}
.flag {
	width: 30px;
}
.titolo1 {
    visibility: hidden;
    position: absolute;
    top: 59px;
    margin-left: 19px;
}
.titolo2 {
    visibility: hidden;
    position: absolute;
    top: 90px;
    margin-left: 19px;
}
.voto {
    visibility: hidden;
    position: absolute;
    top: 130px;
    margin-left: 19px;
    i {
        color: gold;
    }
    
}
.overview {
    visibility: hidden;
    position: absolute;
    top: 166px;
    margin-left: 19px;
    font-size: 13px;
}
.hover {
    visibility: hidden;
    background: rgba(20, 19, 19, 0.87);
    position: absolute;
    height: 519px;
    width: 348px;
    top: 0;
}
.movies:hover .titolo2, .movies:hover .hover, .movies:hover .titolo1, .movies:hover .overview, .movies:hover .voto {
    visibility: visible;
}

</style>