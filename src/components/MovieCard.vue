<template>
    <div class="movie_card border border-white overflow-hidden m-2">
        <div class="movie_info h-100 w-100 text-white p-3 bg-dark">
            <div>{{movie.title}}</div>
            <div>{{movie.original_title}}</div>
            <div>{{movie.original_language}}</div>
            <div>{{movie.vote_average}}</div>
            <div>{{movie.overview}}</div>
        </div>

        <div class="movie_poster">
            <img class="w-100" :src="getImg()" alt="" />
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
               return `http://image.tmdb.org/t/p/w342/${this.movie.poster_path}` 
            } else {
                // da cambiare
                return `https://www.2queue.com/2queue/wp-content/uploads/sites/6/tdomf/4299/movie-poster-coming-soon.png`
            }
        }
    }
    
}
</script>

<style lang="scss" scoped>
.movie_card {
    width: 342px;
    height: 450px;

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