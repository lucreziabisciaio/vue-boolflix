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
            return `https://www.themoviedb.org/t/p/original${this.movie.poster_path}`
        }
    }
    
}
</script>

<style lang="scss" scoped>

</style>