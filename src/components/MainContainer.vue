<template>
    <div class="movies_container bg-secondary">
        <div class="container d-flex justify-content-between align-items-center flex-wrap">

            <movie-card
                v-for="movie in movieList"
                :key="movie.id"
                :movie="movie"
            />

        </div>
    </div>
</template>

<script>
import MovieCard from './MovieCard.vue'

export default {
    components: {
        MovieCard,

    },
    props: {
        movieList: Array,

    }
    
}
</script>

<style lang="scss" scoped>

</style>