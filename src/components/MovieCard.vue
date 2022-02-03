<template>
    <div class="movie_card">
        <div class="movie_poster">
            <img :src="getImg()" alt="">
        </div>
        <div class="title">{{movie.title}}</div>
        <div class="title">{{movie.original_title}}</div>
        <div class="title">{{movie.original_language}}</div>
        <div class="title">{{movie.vote_average}}</div>
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
                return `https://user-images.githubusercontent.com/24848110/33519396-7e56363c-d79d-11e7-969b-09782f5ccbab.png`
            }
        }
    }
    
}
</script>

<style lang="scss" scoped>

</style>