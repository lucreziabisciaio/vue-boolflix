<template>
    <div class="movie_card border border-white m-2">
        <div class="movie_info h-100 text-white p-3 bg-dark">
            <div>{{movie.title}}</div>
            <div>{{movie.original_title}}</div>
            <div>{{movie.original_language}}</div>
            <div>{{movie.vote_average}}</div>
            <div>{{movie.overview}}</div>
        </div>

        <div class="movie_poster">
            <img class="w-100" :src="getImg()" alt="">
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movie: Object
    },
    methods: {
        getImg() {
            if (this.movie.poster_path !== null) {
               return `https://www.themoviedb.org/t/p/w300_and_h450_bestv2/${this.movie.poster_path}` 
            } else {
                // da cambiare
                return `https://user-images.githubusercontent.com/24848110/33519396-7e56363c-d79d-11e7-969b-09782f5ccbab.png`
            }
        }
    }
    
}
</script>

<style lang="scss" scoped>
//stesse w/h dell'img
.movie_card {
    max-width: 300px;
    max-height: 450px;

    position: relative;

    &:hover .movie_info {
        display: block;
    }

    .movie_info {
        display: none;
        position: absolute;
        overflow: auto;
    }
}
</style>