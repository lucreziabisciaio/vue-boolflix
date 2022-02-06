<template>
    <div class="movies_container">
        <div class="container d-flex justify-content-between align-items-center flex-wrap">

            <movie-card :languagesList="languagesList"
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
        languagesList: Array,
        
    }
    
}
</script>

<style lang="scss" scoped>

</style>